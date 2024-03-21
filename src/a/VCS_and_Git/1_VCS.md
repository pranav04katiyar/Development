**Version Control Systems**
---
Version Control Systems are software tools that help manage changes to source code over time. They keep track of every modification to the code in a special kind of database. If a mistake is made, developers can turn back the clock and compare earlier versions of the code to help fix the mistake while minimizing disruption to all team members.

__Why VCS?__
- Collaboration: Allows multiple people to work on the same codebase simultaneously without overwriting each other's work.
- Track Changes: Keeps a comprehensive history of project changes, including who made what changes and when, providing a clear audit trail.
- Revert and Compare: Enables the ability to revert to previous versions of a project, which is crucial for troubleshooting and understanding project evolution.
- Branching and Merging: Facilitates concurrent development by allowing branching (creating another line of development) and merging (bringing different lines of development together).

*Types of Version Control Systems*
-
**Centralized Version Control Systems (CVCS):**
> In CVCS, all files and historical data are stored on a central server. Developers check out files from that central place. Examples: Subversion (SVN) and Perforce.

Pros
 - Simplicity: Easier to understand for beginners.
 - Centralized Control: Administrators have fine-grained control over the repository.

Cons
 - Single Point of Failure: If the central server goes down, no one can collaborate or save versioned changes.
 - Limited Offline Capabilities: Requires connection to the central server for most operations.

**Distributed Version Control Systems (DVCS):**
> In DVCS, each contributor has a complete copy of the entire repository, including its history, on their local machine. Examples: Git and Mercurial.

Pros
 - Full Repository Backup: Every checkout is a full backup of the repository.
 - Enhanced Collaboration: Enables more complex workflows and offline work.

Cons
 - Complexity: Can be more complex to understand and manage, especially for beginners.
 - Larger Repository Size: As each clone is a full copy of the repository, it can take up more space.
