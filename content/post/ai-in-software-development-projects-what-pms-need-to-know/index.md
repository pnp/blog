---
title: "AI in Software Development Projects: What Project Managers need to know"
date: 2025-10-10
author: "Antonio Villarruel"
githubname: a-villarruel
categories: ["Community post"]
images:
- images/orchestra.jpg
tags: ["GitHub Copilot", "Project Management", "AI"]
type: "regular"
---

## Introduction

AI coding assistants like GitHub Copilot are reshaping the way we build software. In the Microsoft ecosystem — with .NET, C#, Azure, and Microsoft 365 — developers are embracing AI to speed up delivery and reduce repetitive work.

But for **Project Managers (PMs)**, this change brings both opportunities and risks. Faster coding doesn’t automatically mean better projects. Without governance, AI-generated code may introduce security flaws, outdated practices, or compliance issues.

This post explores how AI impacts software development projects, and what PMs need to know to ensure success.

---

## Opportunities for Project Management

- **Accelerated delivery**: Developers can use Copilot to scaffold APIs, generate tests, and reduce boilerplate, saving significant time.  
- **Improved developer experience**: Junior team members can onboard faster by learning from AI-generated suggestions.  
- **Knowledge sharing**: Copilot can surface API usage patterns and Microsoft libraries that not everyone knows, acting as a discovery tool.  

---

## Risks to Manage

- **Code quality & technical debt**: AI may suggest outdated .NET APIs or insecure Azure patterns that don’t meet enterprise standards.  
- **Compliance issues**: AI training data may raise intellectual property questions — PMs must align with legal and corporate guidelines.  
- **Over-reliance on AI**: Developers might accept AI suggestions blindly, skipping testing or code reviews.  
- **Skill erosion**: Teams may become too dependent on AI, with less focus on fundamentals.  

---

## Best Practices for PMs in Microsoft Ecosystem Projects

1. **Establish review processes**  
   - Require human peer reviews of all AI-generated code.  
   - Enforce automated quality checks using tools like [Roslyn analyzers](https://learn.microsoft.com/dotnet/fundamentals/code-analysis/overview), SonarQube, or GitHub Actions pipelines.  

2. **Define coding standards**  
   - Align development with Microsoft’s official [.NET coding conventions](https://learn.microsoft.com/dotnet/csharp/fundamentals/coding-style/coding-conventions) and [secure coding guidelines](https://learn.microsoft.com/dotnet/standard/security/).  

3. **Plan for training**  
   - Run workshops on “responsible AI usage in coding” to ensure devs understand strengths and limitations.  

4. **Measure productivity vs. quality**  
   - Track both **velocity** (e.g., story points completed) and **defects** introduced in QA.  
   - Compare trends before and after introducing Copilot.  

5. **Set governance rules**  
   - Define policies on when AI is allowed (e.g., scaffolding vs. critical business logic).  
   - Clarify responsibilities for validating Copilot-generated code.  

---

## Case Example
A Microsoft 365 integration project uses SPFx and .NET APIs. Developers rely on Copilot to quickly generate SharePoint web parts and Graph API queries.  

The PM ensures:  
- **Code reviews** catch deprecated API usage.  
- **CI/CD pipelines** in Azure DevOps enforce linting, unit tests, and security scans.  
- **KPIs** monitor not only delivery speed but also bug density.  

Result: AI accelerates delivery, but quality and governance stay intact.  

---

## Conclusion
AI coding assistants are powerful accelerators — but they don’t replace human expertise or project discipline. For software PMs, the challenge is not to block AI but to **guide its use responsibly**.  

The winning formula is simple: **AI + developers + project governance = successful projects**.  

🎼 *Just like an orchestra needs a conductor, AI-driven development needs a Project Manager — keeping the rhythm, balancing the sections, and ensuring the final performance is in harmony.*  

---

## References & Further Reading

- **Microsoft**  
  - [.NET Coding Conventions](https://learn.microsoft.com/dotnet/csharp/fundamentals/coding-style/coding-conventions)  
  - [.NET Secure Coding Practices](https://learn.microsoft.com/dotnet/standard/security/)  
  - [Azure Security Best Practices](https://learn.microsoft.com/azure/security/fundamentals/best-practices-and-patterns)  

- **GitHub Copilot**  
  - [GitHub Copilot Documentation](https://docs.github.com/copilot)  
  - [Responsible AI with GitHub Copilot](https://github.blog/2023-02-14-github-copilot-responsible-ai-principles/)  

- **Project Management Institute (PMI)**  
  - [AI and Project Management: Opportunities and Challenges](https://www.pmi.org/learning/library/ai-project-management-12844)  
  - [PMI Standards and Frameworks](https://www.pmi.org/standards)  