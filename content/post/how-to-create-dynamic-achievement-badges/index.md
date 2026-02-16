---
title: "Microsoft Lists: Create Dynamic Achievement Badge with Column Formatting"
date: 2025-09-26T00:00:00-00:00
author: "Sai Siva Ram Bandaru"
githubname: saiiiiiii
categories: ["Community post"]
images:
- images/sharepoint-badge-column-formatting.png
tags: ["Microsoft Lists", "SharePoint"]
type: "regular"
draft: false
---

## Introduction

Gamification has become a powerful tool for driving engagement, recognizing achievement, and motivating users in digital platforms. Microsoft Lists and SharePoint can leverage these principles through creative column formatting to create dynamic badge systems that visually represent user performance, contribution levels, or achievement tiers.

In this post, we'll explore how to build a sophisticated achievement badge system using column formatting JSON. This solution creates tier-based badges with custom images, colored borders, and medal indicators that automatically adjust based on score values—transforming simple numeric data into an engaging visual recognition system.

Achievement badges provide immediate visual feedback, create clear progression paths, and make data more engaging and memorable. Whether you're tracking employee contributions, student performance, customer loyalty points, or team achievements, this dynamic badge system brings your data to life.

![Gamification Example](./images/sharepoint-badge-column-formatting.png)

## What We're Building

Our solution creates a dynamic, three-tier achievement badge system featuring:

- **Conditional badge images** that change based on score thresholds (Rookie, Ace, Champion)
- **Tier-specific colored borders** for instant visual recognition
- **Medal indicators** with emoji badges (🥉 Bronze, 🥈 Silver, 🥇 Gold)
- **Hover tooltips** displaying tier names and exact scores
- **Position-absolute badge overlays** for professional design
- **Responsive sizing** (100×100px) suitable for various layouts

The system uses mathematical comparisons and conditional logic to automatically assign the appropriate badge, border color, and medal based on the user's score, creating a complete gamification experience without any custom code or external dependencies.

## List Requirements

Create a SharePoint list or Microsoft List with the following column structure:

| Internal Name | Type | Description |
|---------------|------|-------------|
| Score | Number | Numerical score value for determining Gamification level |
| EmployeeName | Single Line of Text | Employee Name |
| Title | Single Line of Text | Column where the formatting will be applied |

> **Note:** You'll also need to upload three badge images to your SharePoint site's SiteAssets library: `Rookie.png`, `Ace.png`, and `Champion.png`. These should be visually distinct images representing each achievement tier.

### Badge Image Setup

1. Navigate to your SharePoint site
2. Go to **Site Contents** > **Site Assets** (or create this library if it doesn't exist)
3. Upload your three badge images:
   - `Rookie.png` - For scores 0-30
   - `Ace.png` - For scores 31-149
   - `Champion.png` - For scores 150+

**Image Requirements:**
- Format: PNG with transparent background (recommended)
- Dimensions: 300×300px minimum (will be scaled to 100×100px)
- File size: Under 100KB for optimal performance
- Style: Should visually represent progression (e.g., bronze → silver → gold)

## Sample Data

Here's example data to populate your list:

| Title | Score |
|-------|-------|
| Sai | 25 |
| Budvik | 87 |

**Expected Badge Results:**
- Sai (25) → Rookie badge with gray border and bronze medal
- Budvik (87) → Ace badge with blue border and silver medal

## The Achievement Tier System

### Tier Definitions

The badge system implements three distinct achievement tiers:

| Tier | Score Range | Badge Image | Border Color | Medal | Color Code |
|------|-------------|-------------|--------------|-------|------------|
| **Rookie** | 0 - 30 | Rookie.png | Gray | 🥉 Bronze | #6c757d |
| **Ace** | 31 - 149 | Ace.png | Blue | 🥈 Silver | #007acc |
| **Champion** | 150+ | Champion.png | Gold | 🥇 Gold | #ffc107 |

### Conditional Logic Architecture

The system uses nested `if()` statements to evaluate scores and assign appropriate visual elements:

```
if(Number([$Score]) <= 30, 
    'Rookie Properties',
    if(Number([$Score]) <= 149,
        'Ace Properties',
        if(Number([$Score]) >= 150,
            'Champion Properties',
            'Default Properties'
        )
    )
)
```

**Logic Flow:**
1. Check if score ≤ 30 → Assign Rookie tier
2. Else check if score ≤ 149 → Assign Ace tier
3. Else check if score ≥ 150 → Assign Champion tier
4. Else assign default (fallback)

### Image Source Dynamic Selection

The badge image is dynamically selected using the current web URL concatenated with the appropriate filename:

```json
"src": "=if(Number([$Score]) <= 30, 
    @currentWeb+'/SiteAssets/Rookie.png', 
    if(Number([$Score]) <= 149, 
        @currentWeb+'/SiteAssets/Ace.png', 
        if(Number([$Score]) >= 150, 
            @currentWeb+'/SiteAssets/Champion.png', 
            @currentWeb+'/SiteAssets/Rookie.png'
        )
    )
)"
```

**Key Components:**
- `@currentWeb` - SharePoint token that resolves to the current site's URL
- `/SiteAssets/` - Standard document library path
- Dynamic filename based on score evaluation
- Fallback to Rookie.png if conditions fail

## Design Architecture Breakdown

### Container Structure

The root element uses inline-flex for precise positioning:

```json
{
  "elmType": "div",
  "style": {
    "display": "inline-flex",
    "align-items": "center",
    "justify-content": "center",
    "position": "relative"
  }
}
```

**Design Decisions:**
- **inline-flex** - Allows badge to sit inline with other content while using flex properties
- **center alignment** - Ensures badge and medal are perfectly centered
- **position: relative** - Creates positioning context for the absolute medal overlay

### Badge Image Styling

The main image element with dynamic properties:

```json
{
  "elmType": "img",
  "attributes": {
    "src": "[dynamic image path]",
    "title": "[dynamic tooltip text]"
  },
  "style": {
    "width": "100px",
    "height": "100px",
    "border": "[dynamic border color and width]",
    "cursor": "pointer"
  }
}
```

**Style Properties:**
- **Fixed dimensions** (100×100px) - Ensures consistent sizing across all badges
- **3px solid border** - Creates clear tier distinction with conditional colors
- **pointer cursor** - Indicates interactivity and encourages hover for tooltip

### Tooltip Implementation

The title attribute creates informative hover text:

```json
"title": "=if(Number([$Score]) <= 30, 
    'Rookie Contributor - Score: ' + [$Score], 
    if(Number([$Score]) <= 149, 
        'Ace Contributor - Score: ' + [$Score], 
        if(Number([$Score]) >= 150, 
            'Champion - Score: ' + [$Score], 
            'Contributor - Score: ' + [$Score]
        )
    )
)"
```

**Tooltip Features:**
- Displays tier name and exact score
- Uses string concatenation with `+ [$Score]`
- Provides context without cluttering the visual design

### Medal Overlay Badge

The position-absolute medal indicator:

```json
{
  "elmType": "div",
  "style": {
    "position": "absolute",
    "bottom": "-2px",
    "right": "-2px",
    "width": "18px",
    "height": "18px",
    "border-radius": "50%",
    "background-color": "[dynamic color]",
    "border": "2px solid white",
    "display": "flex",
    "align-items": "center",
    "justify-content": "center",
    "font-size": "10px",
    "color": "white",
    "font-weight": "bold"
  },
  "txtContent": "[dynamic medal emoji]"
}
```

**Positioning Strategy:**
- **bottom: -2px, right: -2px** - Places medal slightly outside the badge for overlap effect
- **18×18px circular badge** - Small enough to not obscure, large enough to see clearly
- **2px white border** - Creates separation from badge background
- **Flexbox centering** - Perfectly centers emoji within circle

### Medal Emoji Assignment

Conditional medal selection based on tier:

```json
"txtContent": "=if(Number([$Score]) <= 30, 
    '🥉', 
    if(Number([$Score]) <= 149, 
        '🥈', 
        if(Number([$Score]) >= 150, 
            '🥇', 
            '⭐'
        )
    )
)"
```

**Medal Meanings:**
- 🥉 Bronze - Rookie tier (beginner achievement)
- 🥈 Silver - Ace tier (intermediate achievement)
- 🥇 Gold - Champion tier (top achievement)
- ⭐ Star - Fallback (default indicator)

## How to Implement

### Step 1: Prepare Badge Images

1. **Design or source three badge images** representing your tier levels:
   - Use consistent visual style across all badges
   - Consider progressive design (simple → elaborate)
   - Ensure good visibility at 100×100px size

2. **Upload to SharePoint Site Assets**:
   - Navigate to your site's **Site Assets** library
   - Upload `Rookie.png`, `Ace.png`, and `Champion.png`
   - Verify files are publicly accessible (not checked out)

3. **Test image URLs** by navigating to:
   ```
   https://yoursite.sharepoint.com/sites/yoursite/SiteAssets/Rookie.png
   ```

### Step 2: Create Your List

1. Create a new Microsoft List or SharePoint list
2. Add a **Number** column named "Score"
3. Configure Score column:
   - Min value: 0
   - Max value: (unlimited or set your max, e.g., 1000)
   - Decimal places: 0 (for whole numbers)
4. Populate with sample data for testing

### Step 3: Apply Column Formatting

1. Click on the **Title** column header (or create a dedicated "Badge" calculated column)
2. Select **Column settings** > **Format this column**
3. Choose **Advanced mode**
4. Paste the provided JSON code
5. Click **Preview** to verify the badges display correctly
6. Click **Save** to apply the formatting

### Step 4: Test All Tiers

Create test items with scores across all ranges:
- **0-30** → Verify Rookie badge, gray border, bronze medal
- **31-149** → Verify Ace badge, blue border, silver medal
- **150+** → Verify Champion badge, gold border, gold medal
- Hover over badges to confirm tooltips display correctly

## Advanced Customization Options

### Adjusting Tier Thresholds

Modify score ranges to fit your use case:

**Four-Tier System:**
```json
"=if(Number([$Score]) <= 30, 
    'Rookie', 
    if(Number([$Score]) <= 99, 
        'Intermediate', 
        if(Number([$Score]) <= 199, 
            'Advanced', 
            if(Number([$Score]) >= 200, 
                'Expert', 
                'Default'
            )
        )
    )
)"
```

**Percentage-Based System (0-100):**
```json
"=if(Number([$Score]) < 60, 
    'Needs Improvement', 
    if(Number([$Score]) < 80, 
        'Satisfactory', 
        if(Number([$Score]) >= 80, 
            'Excellent', 
            'Default'
        )
    )
)"
```

### Custom Color Schemes

#### Corporate Branding Theme
```json
"border": "=if(Number([$Score]) <= 30, 
    '3px solid #E0E0E0',  // Light Gray
    if(Number([$Score]) <= 149, 
        '3px solid #0078D4',  // Microsoft Blue
        if(Number([$Score]) >= 150, 
            '3px solid #FFB900',  // Gold
            '3px solid #107C10'   // Green fallback
        )
    )
)"
```

### Badge Size Variations

#### Compact Badges (60×60px)
```json
"style": {
  "width": "60px",
  "height": "60px",
  "border": "[dynamic border]"
}
```

Adjust medal overlay accordingly:
```json
"style": {
  "width": "14px",
  "height": "14px",
  "bottom": "-1px",
  "right": "-1px",
  "font-size": "8px"
}
```

#### Large Badges (150×150px)
```json
"style": {
  "width": "150px",
  "height": "150px",
  "border": "5px solid [color]"
}
```

Adjust medal overlay:
```json
"style": {
  "width": "28px",
  "height": "28px",
  "bottom": "-3px",
  "right": "-3px",
  "font-size": "14px"
}
```

### Alternative Medal Indicators

#### Star Rating System
```json
"txtContent": "=if(Number([$Score]) <= 30, 
    '⭐', 
    if(Number([$Score]) <= 149, 
        '⭐⭐', 
        if(Number([$Score]) >= 150, 
            '⭐⭐⭐', 
            '⭐'
        )
    )
)"
```

#### Number Badges
```json
"txtContent": "=if(Number([$Score]) <= 30, 
    '1', 
    if(Number([$Score]) <= 149, 
        '2', 
        if(Number([$Score]) >= 150, 
            '3', 
            '0'
        )
    )
)"
```

#### Custom Icons (Unicode)
```json
"txtContent": "=if(Number([$Score]) <= 30, 
    '🌱',  // Seedling
    if(Number([$Score]) <= 149, 
        '🌳',  // Tree
        if(Number([$Score]) >= 150, 
            '🏆',  // Trophy
            '✨'
        )
    )
)"
```

### Adding Animation Effects

While SharePoint column formatting doesn't support CSS animations directly, you can add subtle effects through styling:

#### Glow Effect on Borders
```json
"box-shadow": "=if(Number([$Score]) >= 150, 
    '0 0 15px #ffc107', 
    if(Number([$Score]) <= 149, 
        '0 0 10px #007acc', 
        '0 0 5px #6c757d'
    )
)"
```

#### Scale on Hover (Limited Support)
```json
"transform": "=if(Number([$Score]) >= 150, 
    'scale(1.1)', 
    'scale(1)'
)"
```

### Multiple Badge Criteria

Combine score with other columns for complex logic:

```json
"src": "=if([$Status] == 'Active' && Number([$Score]) >= 150, 
    @currentWeb+'/SiteAssets/ActiveChampion.png',
    if(Number([$Score]) >= 150,
        @currentWeb+'/SiteAssets/Champion.png',
        if(Number([$Score]) <= 30,
            @currentWeb+'/SiteAssets/Rookie.png',
            @currentWeb+'/SiteAssets/Ace.png'
        )
    )
)"
```

## Use Cases and Applications

### Employee Recognition Programs
Track and visualize employee contributions, performance scores, or engagement levels with automatic tier promotions as scores increase.

### Learning Management Systems
Display student progress through course materials with achievement badges for completion milestones, quiz scores, or skill certifications.

### Customer Loyalty Programs
Visualize customer loyalty tiers (Bronze, Silver, Gold) based on purchase history, reward points, or engagement metrics.

### Project Contribution Tracking
Recognize team member contributions to projects with badges based on commits, tasks completed, or hours contributed.

### Sales Performance Dashboards
Display sales representative performance tiers with visual badges for quarterly or annual achievement levels.

### Community Engagement Platforms
Reward community members for participation with visible badges based on posts, helpful answers, or community reputation scores.

### Certification and Compliance Tracking
Show certification levels or compliance status with clear visual indicators for different achievement or requirement tiers.

### Gamified Task Management
Add engagement to task tracking by awarding badges based on tasks completed, projects delivered, or goals achieved.

## Performance and Technical Considerations

### Image Loading Performance

**Best Practices:**
- Keep badge images under 50KB each
- Use PNG format with transparency
- Consider using SVG for scalable, small file sizes
- Host images in the same site collection for faster loading

**Caching Benefits:**
- SharePoint automatically caches Site Assets images
- First load may be slower; subsequent loads are instant
- Consider preloading images if list will be heavily used

### Score Calculation Methods

The `Number()` function ensures proper numeric comparison:

```json
Number([$Score])
```

**Why This Matters:**
- SharePoint columns can sometimes be treated as text
- `Number()` converts to numeric type for reliable comparisons
- Prevents issues like "30" > "149" (string comparison)

### Browser Compatibility

**Fully Supported:**
- Chrome (latest)
- Edge (latest)
- Firefox (latest)
- Safari (latest)

**Features Used:**
- Flexbox (excellent support)
- Position absolute/relative (universal support)
- Border-radius (fully supported)
- Emoji rendering (may vary slightly by OS/browser)

### Mobile Responsiveness

The badge system works well on mobile devices:
- Fixed pixel sizing ensures consistency
- Touch-friendly 100×100px size
- Tooltips work on long-press (mobile)
- Consider reducing to 75×75px for very small screens

## Troubleshooting Guide

### Badges Not Displaying

**Issue:** Images don't appear, showing broken image icons

**Solutions:**
1. Verify image files exist in Site Assets:
   ```
   https://[yoursite].sharepoint.com/sites/[sitename]/SiteAssets/
   ```
2. Check file names match exactly (case-sensitive):
   - `Rookie.png` not `rookie.png` or `Rookie.PNG`
3. Ensure files aren't checked out
4. Verify current user has read permissions to Site Assets
5. Try accessing image URL directly in browser

**Issue:** Wrong badge displays for score

**Solutions:**
- Verify Score column is type "Number" not "Text"
- Check that `Number()` function is wrapping `[$Score]`
- Review your tier thresholds (≤30, ≤149, ≥150)
- Test with exact threshold values (30, 149, 150)

### Medal Overlay Problems

**Issue:** Medal doesn't appear or is mispositioned

**Solutions:**
1. Verify parent div has `position: relative`
2. Check bottom/right negative values: `-2px`
3. Ensure emoji is rendering (some systems may not support all emojis)
4. Try alternative emojis if current ones don't display

**Issue:** Medal is too large or too small

**Solutions:**
- Adjust width/height (currently 18×18px)
- Modify font-size for emoji (currently 10px)
- Scale proportionally with badge size

### Border Color Issues

**Issue:** Border colors don't change with score

**Solutions:**
1. Verify conditional logic in border style property
2. Check color hex codes are properly formatted (#rrggbb)
3. Ensure Score column contains valid numbers
4. Test with border-width: 5px for more visibility

**Issue:** All borders same color

**Solutions:**
- Review if() statement syntax
- Verify commas separating conditions
- Check for missing closing parentheses
- Validate JSON with online validator

### Tooltip Problems

**Issue:** Tooltip doesn't show on hover

**Solutions:**
1. Verify `title` attribute in img element
2. Ensure string concatenation syntax: `'text' + [$Score]`
3. Check browser allows native tooltips (not blocked)
4. Try hovering longer (some browsers have delay)

**Issue:** Tooltip shows "undefined" or "[object Object]"

**Solutions:**
- Ensure Score column contains valid numbers
- Convert to string if needed: `'' + [$Score]`
- Check for null values in Score column

## Advanced Implementation Patterns

### Dynamic Progress Bars with Badges

Combine badge with a progress bar:

```json
{
  "elmType": "div",
  "style": {
    "display": "flex",
    "align-items": "center",
    "gap": "12px"
  },
  "children": [
    {
      "elmType": "img",
      "attributes": {
        "src": "[badge logic]"
      },
      "style": {
        "width": "60px",
        "height": "60px"
      }
    },
    {
      "elmType": "div",
      "style": {
        "flex": "1",
        "height": "20px",
        "background-color": "#e0e0e0",
        "border-radius": "10px",
        "overflow": "hidden"
      },
      "children": [
        {
          "elmType": "div",
          "style": {
            "width": "=[$Score] + '%'",
            "height": "100%",
            "background-color": "#4caf50"
          }
        }
      ]
    }
  ]
}
```

### Multi-Badge Achievement System

Display multiple badges for different categories:

```json
{
  "elmType": "div",
  "style": {
    "display": "flex",
    "gap": "8px"
  },
  "children": [
    {
      "elmType": "img",
      "attributes": {
        "src": "=[badge logic for Score]"
      },
      "style": {
        "width": "50px",
        "height": "50px"
      }
    },
    {
      "elmType": "img",
      "attributes": {
        "src": "=[badge logic for Quality]"
      },
      "style": {
        "width": "50px",
        "height": "50px"
      }
    },
    {
      "elmType": "img",
      "attributes": {
        "src": "=[badge logic for Speed]"
      },
      "style": {
        "width": "50px",
        "height": "50px"
      }
    }
  ]
}
```

### Badge with Numeric Score Overlay

Show both badge and exact score:

```json
{
  "elmType": "div",
  "style": {
    "position": "relative",
    "display": "inline-flex"
  },
  "children": [
    {
      "elmType": "img",
      "attributes": {
        "src": "[badge logic]"
      },
      "style": {
        "width": "100px",
        "height": "100px"
      }
    },
    {
      "elmType": "div",
      "style": {
        "position": "absolute",
        "bottom": "8px",
        "left": "50%",
        "transform": "translateX(-50%)",
        "background-color": "rgba(0,0,0,0.7)",
        "color": "white",
        "padding": "2px 8px",
        "border-radius": "12px",
        "font-size": "14px",
        "font-weight": "bold"
      },
      "txtContent": "[$Score]"
    }
  ]
}
```


## Integration with Microsoft 365 Ecosystem

### Power Automate Integration

Create flows triggered by score changes:

**Scenario: Send congratulations email when user reaches Champion tier**
1. Trigger: When item is modified
2. Condition: Score ≥ 150 and Previous Score < 150
3. Action: Send email with achievement notification

### Power Apps Integration

Build custom forms with badge preview:

```javascript
// In Power Apps, reference the Score field
If(Score <= 30, 
    Image1.Image = "https://yoursite.sharepoint.com/.../Rookie.png",
    If(Score <= 149,
        Image1.Image = "https://yoursite.sharepoint.com/.../Ace.png",
        Image1.Image = "https://yoursite.sharepoint.com/.../Champion.png"
    )
)
```

### Power BI Integration

Create dashboards showing badge distribution:
- Count of users per tier
- Average score by tier
- Trend analysis of tier promotions over time
- Leaderboard visualizations

## Security and Compliance Considerations

### Data Privacy

**Considerations:**
- Badges publicly display achievement levels
- Consider who should see scores vs. just badges
- Use SharePoint permissions to control list access
- Consider separate views for managers vs. team members

### Access Control

**Image Security:**
- Site Assets should have appropriate read permissions
- Consider if external users need badge access
- Verify image permissions match list permissions

### Audit and Tracking

**Score Modifications:**
- Enable versioning on the list to track score changes
- Use SharePoint audit logs to monitor score updates
- Consider workflow approvals for manual score adjustments

## Accessibility Considerations

### Screen Reader Support

**Current Implementation:**
- Title attribute provides context for screen readers
- Consider adding `alt` attribute to images
- Emoji may not be read consistently

**Enhanced Accessibility:**
```json
"attributes": {
  "src": "[badge logic]",
  "alt": "=if(Number([$Score]) <= 30, 
      'Rookie level achievement badge', 
      if(Number([$Score]) <= 149, 
          'Ace level achievement badge', 
          'Champion level achievement badge'
      )
  )",
  "title": "[existing tooltip]",
  "aria-label": "='Achievement badge showing ' + if(Number([$Score]) <= 30, 'Rookie', if(Number([$Score]) <= 149, 'Ace', 'Champion')) + ' tier with score of ' + [$Score]"
}
```

### Color Contrast

Ensure border colors meet WCAG AA standards:
- Gray (#6c757d) - Adequate contrast
- Blue (#007acc) - Good contrast
- Gold (#ffc107) - May need adjustment on white backgrounds

Consider adding text labels for color-blind users:
```json
{
  "elmType": "span",
  "style": {
    "font-size": "12px",
    "margin-top": "4px"
  },
  "txtContent": "=if(Number([$Score]) <= 30, 'Rookie', if(Number([$Score]) <= 149, 'Ace', 'Champion'))"
}
```

## Performance Optimization

### Image Optimization Checklist

- [ ] Compress images to <50KB each
- [ ] Use consistent aspect ratio (1:1 for circles)
- [ ] Consider CDN for frequently accessed images
- [ ] Implement lazy loading for large lists
- [ ] Use WebP format where supported

### List Performance

**For Large Lists (1000+ items):**
- Index the Score column
- Use filtered views for different tiers
- Consider pagination settings
- Limit columns in view to essentials

### Caching Strategy

SharePoint handles image caching automatically, but consider:
- Version badge images when updating (e.g., Rookie_v2.png)
- Clear browser cache after image updates
- Test with different networks (office vs. remote)

## Testing Checklist

### Functional Testing

- [ ] Rookie tier (score 0-30) displays correctly
- [ ] Ace tier (score 31-149) displays correctly
- [ ] Champion tier (score 150+) displays correctly
- [ ] Tooltips show correct information
- [ ] Borders match tier colors
- [ ] Medals display appropriate emojis
- [ ] All images load successfully
- [ ] Works in all supported browsers
- [ ] Mobile responsive display verified
- [ ] Null/empty scores handled gracefully

### Edge Cases

- [ ] Score = 0 (minimum)
- [ ] Score = 30 (tier boundary)
- [ ] Score = 31 (just above boundary)
- [ ] Score = 149 (tier boundary)
- [ ] Score = 150 (tier boundary)
- [ ] Score = 999+ (very high scores)
- [ ] Negative scores (if applicable)
- [ ] Decimal scores (should round or truncate)


## Conclusion

Dynamic achievement badge systems transform simple numeric data into engaging, motivating visual experiences. By leveraging SharePoint's column formatting capabilities with conditional logic and creative design, we can create sophisticated gamification elements without custom development or external dependencies.

This solution demonstrates how thoughtful application of JSON formatting can produce professional, scalable recognition systems that drive engagement, celebrate achievement, and provide clear visual feedback on performance and progress.

Whether you're building employee recognition programs, student tracking systems, customer loyalty platforms, or any scenario requiring visual achievement representation, this badge system provides a solid foundation that can be customized to match your specific branding, thresholds, and recognition philosophy.

Start recognizing achievements visually today and watch engagement soar!


## GitHub Code

- [sharepoint-generic-gamification](https://github.com/pnp/List-Formatting/tree/master/column-samples/generic-gamification)

## Additional Resources

- [SharePoint Column Formatting Documentation](https://docs.microsoft.com/en-us/sharepoint/dev/declarative-customization/column-formatting)
- [SharePoint JSON Schema Reference](https://developer.microsoft.com/json-schemas/sp/v2/column-formatting.schema.json)
- [PnP Community - List Formatting Samples](https://github.com/pnp/List-Formatting)
- [Microsoft Lists Advanced Formatting Examples](https://docs.microsoft.com/en-us/sharepoint/dev/declarative-customization/column-formatting#examples)
- [CSS Flexbox Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
