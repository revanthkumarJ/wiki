# **Git Commit Message Style Guide**

## **Commit Messages**

### **Message Structure**

A commit message consists of three distinct parts separated by a blank line:  

1. **Title**: Contains the type and subject (mandatory).  
2. **Body**: Provides additional details or context (optional).  
3. **Footer**: Includes metadata like issue references or breaking changes (optional).  

The layout looks like this:  

```plaintext
type: subject

body

footer
```

---
## **Title**

The **title** consists of two parts:  
1. **Type**: Indicates the category of the commit.  
2. **Subject**: A concise description of the change.


### **The Type**

The type specifies the nature of the commit and must be one of the following:  

- **feat**: A new feature.  
- **fix**: A bug fix.  
- **docs**: Changes to documentation.  
- **style**: Code style changes (e.g., formatting, missing semicolons) without logic changes.  
- **refactor**: Refactoring code without altering external behavior.  
- **test**: Adding or updating tests without affecting production code.  
- **chore**: Maintenance tasks (e.g., updating build tools or configs) with no production code changes.  


### **The Subject**

- Limit the subject to **50 characters** or fewer.  
- Start with a **capital letter**.  
- Avoid ending the subject with a period.  

**Tip**: Use an **imperative tone** to describe what the commit does.  
For example:  
- Use *"Change"* instead of *"Changed"* or *"Changes"*.
## **The Body**

The body is **optional** and should only be used when the commit requires further explanation or context. It helps clarify **what** the commit does and **why** it is necessary. Avoid explaining **how** the changes were made, as that information is usually captured in the code itself.

### **Guidelines for the Body:**

- Leave a blank line between the title and the body.  
- Limit the length of each line in the body to **72 characters** for readability.  
- Be concise but informative. Use the body to clarify complex commits that are not immediately obvious from the title.  
