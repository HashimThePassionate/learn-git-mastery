### Centralized Workflow:
In a centralized workflow, there's a single repository where all collaborators push their changes. Each contributor clones the central repository, makes changes locally, and then pushes them back. This simplicity makes it easy to manage, especially for smaller teams, but can lead to bottlenecks and conflicts as all changes are funneled through one location.

**Advantages:**
1. **Simplicity:** Easy to understand and set up, suitable for small teams.
2. **Control:** Offers a centralized point of control over the project's history and updates.

**Disadvantages:**
1. **Single Point of Failure:** If the central repository goes down, collaborators can't push changes.
2. **Potential Bottlenecks:** A bottleneck can occur when many developers try to push changes simultaneously.

**Example:** The Linux Kernel development initially followed a centralized workflow, where Linus Torvalds managed the main repository, and developers submitted patches to him for approval and integration.
```
          Collaborator 1         Collaborator 2
                 |                       |
                 v                       v
          Central Repository (master/main)
``` 
### Distributed Workflow:
In a distributed workflow, each developer has their own repository, and changes are shared between them. Developers pull changes from each other's repositories and push to their own. This decentralization fosters greater independence and flexibility but can require more coordination and communication.

**Advantages:**
1. **Flexibility:** Developers can work offline and push changes when ready.
2. **Redundancy:** Multiple copies of the repository reduce the risk of data loss.

**Disadvantages:**
1. **Complexity:** Requires more coordination and communication among developers.
2. **Consistency:** Maintaining consistency across repositories can be challenging.

**Example:** The development of the Git version control system itself follows a distributed workflow, where each developer has their own repository and contributes changes through pull requests.

```
   Collaborator 1             Collaborator 2
        |                           |
        v                           v
Local Repository 1           Local Repository 2
        |                           |
        v                           v
      Remote Repository (shared)
``` 
### Integration-Manager Workflow:
In an integration-manager workflow, there's a central repository with a designated integration manager who accepts changes from contributors. Developers fork the central repository, make changes in their forks, and then submit pull requests to the integration manager for review and integration. This workflow provides a balance between centralization and decentralization.

**Advantages:**
1. **Controlled Integration:** Changes are reviewed and integrated by a designated person, ensuring quality and consistency.
2. **Flexibility:** Contributors can work independently in their forks and submit changes when ready.

**Disadvantages:**
1. **Potential Bottlenecks:** The integration manager can become a bottleneck if there are many pull requests to review.
2. **Dependency on Integration Manager:** Development pace can be affected if the integration manager is unavailable or overwhelmed.

**Example:** The development of the Ruby on Rails framework follows an integration-manager workflow, where contributors fork the main repository on GitHub, make changes in their forks, and then submit pull requests to the core team for review and integration.
```
          Collaborator 1         Collaborator 2
                 |                       |
                 v                       v
          Integration Manager (Reviews & Merges)
                        |
                        v
                Central Repository
``` 