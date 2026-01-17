---
title: "Why Version Control Exists"
datePublished: Sat Jan 17 2026 13:25:54 GMT+0000 (Coordinated Universal Time)
cuid: cmkicbthp000702l51oko2e6x
slug: why-version-control-exists
tags: software-development, development, version-control, git, learn

---

Hello 👋 this is my first blog.  
Let’s understand why version control exists by looking at how developers shared code before tools like Git.

## Phase 1 (The Pen drive Story)

A solo developer starts building an e-commerce website. Initially, all parts of the project are handled by the developer himself. As the project grows, he soon realizes that building a complete e-commerce platform alone is a heavy burden. To reduce this load, he decides to hire a freelance developer to handle specific tasks such as payment gateway integration, traffic load management, and other responsibilities he wants to delegate.

To share the current codebase, the main developer creates a zip file of the project named “e-commerce\_project.zip” and sends it to the freelancer. The freelancer completes the assigned tasks, updates the codebase, and sends back another zip file—let’s call it “*e-commerce\_project\_final.zip”*.

The main developer extracts the updated project and runs the application, only to find his terminal filled with errors. Features that were previously working correctly start failing, and debugging becomes difficult. With no clear visibility into what changes were made, the developer has to contact the freelancer and manually go through the codebase to understand what went wrong. The story ends there.

Even though such a failure may not happen every time, this scenario gives us a clear idea of the potential problems with this approach. Let’s break them down. If you notice any that I missed, feel free to mention them in the comments.

### Drawbacks List

* Slow collaboration: No parallel development is possible; only one developer can effectively work at a time.
    
* No codebase history: It is difficult to identify what changes were made and by whom.
    
* No reliable version history: A new zip file must be manually created after every update, making the process error-prone.
    
* No single source of truth: Multiple saved copies (final, final\_v2, latest) create confusion about which version is correct.
    
* No safe rollback mechanism: If the code breaks, finding a stable version becomes difficult.
    
* Does not scale: This approach breaks down as the team grows, since parallel development is not supported.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1768652994853/4de89987-3b1f-4d21-806b-015bc9d8f61d.png align="center")

## Phase 2 ( Thinking About a Potential Solution)

After understanding the problems highlighted in the previous phase, a possible solution starts to take shape. One idea that naturally comes to mind is creating a **local change tracking system**—let’s call it **CTS (Change Tracking System)**.

The goal of this system is simple:  
to track changes made to the codebase locally before sharing it with another developer.

Such a system could record basic but important information like:

1. What changes are being made to the codebase
    
2. Who is making those changes
    
3. When the changes were made
    
4. Why the changes were made (using developer-written messages)
    

Once a developer completes their assigned task, they can share the updated codebase along with this change history file. The other developer can then continue working on the project and repeat the same process.

How CTS Solves Problems From Phase 1

Let’s now analyze how introducing this **single variable (CTS)** impacts the problems we identified earlier.

### The Scorecard: CTS vs. The Problems

### Solved

* **Codebase History:** Since CTS records every change, we finally have a reliable timeline of updates.
    
* **Rollback Mechanism:** We can now identify and revert to stable versions because we track who, when, and why.
    

### Still Broken

* **Slow Collaboration:** We are still passing zip files around. Parallel work is impossible.
    
* **No Single Source of Truth:** We still have final\_v1.zip and final\_v2.zip floating around different computers.
    
* **Scaling:** As the team grows, this manual sharing process falls apart.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1768653297151/de13a677-1163-43ff-bdb1-774b23933afd.png align="center")

## Phase 3 — The Introduction of Version Control System (VCS)

From Phase 2, one major problem still remains unresolved:  
we **do not have a single source of truth** that every developer can rely on.

Each developer still maintains their own local copy of the project, along with separate change histories. Even though we introduced a local Change Tracking System (CTS), collaboration is still limited because the codebase itself is not shared in a unified way.

To solve this, we need to move beyond local tracking.

### Introducing a Central Source of Truth

The idea is simple:

> Move the local CTS to a **central location** that every developer can access.

In practical terms, this means:

* Storing the codebase on a **central server**
    
* Keeping the entire change history in that shared location
    
* Allowing developers to push their changes to, and pull updates from, the same place
    

This central system becomes the **single, agreed-upon version of the project**.

### How This Solves the Remaining Problems

Let’s revisit the problems we could not solve in Phase 2 and see how this change fixes them.

* **Slow Collaboration & Scaling: SOLVED.** Because the server is always available, developers don't have to wait for each other. Parallel development is now possible, whether you have 2 developers or 200.
    
* **Single Source of Truth: SOLVED.** There is no more confusion about which version is "final." If it’s on the server, it is the truth.
    

### What We’ve Built So Far

At this point, our system consists of:

* A **change tracking mechanism** (what changed, who changed it, when, and why)
    
* A **central server** accessible to all developers
    
* A workflow that supports collaboration, history, rollback, and scalability
    

This combined system is what we formally call a **Version Control System (VCS)**.

When this system is backed by a shared server, it is commonly referred to as a **remote version control system**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1768653772418/87bd6a44-e757-4272-aaf3-570f8e559ef5.png align="center")

In this blog, we focused on *why* version control exists.  
In the next blog, we’ll formally define a Version Control System (VCS), look at its key features, and understand why **Git** is the most widely used VCS today.

**Up next:** *Git for Beginners: Basics and Essential Commands*