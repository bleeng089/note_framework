
**Ticket Title**:  
[Short Description of the Issue] - [Context or Feature Name]  
*Example*: "NullPointerException in User Login Function"

**Ticket Type**:  
- Bug (for issues in existing code)  
- Task (for new troubleshooting or investigation tasks)

**Priority**:  
- Low (minor issue, no immediate impact)  
- Medium (affects functionality but has workarounds)  
- High (blocks progress or critical functionality)  
- Urgent (showstopper, needs immediate attention)

**Assignee**:  
[Student's Name or Team Name]

**Labels**:  
- `troubleshooting`  
- `code-issue`  
- [Language/Technology, e.g., `python`, `javascript`, `java`]  
- [Feature/Module, e.g., `authentication`, `database`]  

**Components**:  
[Relevant project module, e.g., "Frontend", "Backend", "Database"]

---

### Description (Main Body)

**1. Summary of the Issue**:  
- Describe the problem in 1-2 sentences. Be specific about what’s not working.  
*Example*: "When a user tries to log in with valid credentials, the application crashes with a NullPointerException."

**2. Steps to Reproduce**:  
- List the exact steps to replicate the issue. Number each step for clarity.  
*Example*:  
  1. Navigate to the login page.  
  2. Enter a valid username and password.  
  3. Click the "Login" button.  
  4. Observe the crash with an error message.

**3. Expected Behavior**:  
- Describe what should happen when the code works correctly.  
*Example*: "The user should be redirected to the dashboard page upon successful login."

**4. Actual Behavior**:  
- Describe what actually happens, including any error messages or logs.  
*Example*: "The application crashes, and the console displays: `NullPointerException at LoginService.java:45`."

**5. Environment Details**:  
- Specify the environment where the issue occurs.  
  - Programming language: [e.g., Python 3.9]  
  - Framework/Library: [e.g., Flask 2.0]  
  - Operating System: [e.g., Windows 11]  
  - Other dependencies: [e.g., MySQL 8.0]  
  - Testing context: [e.g., Local development, Unit test]

**6. Code Snippet**:  
- Include the relevant code causing the issue (use code formatting, e.g., triple backticks ```). Keep it concise.  
*Example*:  
```java
public User login(String username, String password) {
    User user = userRepository.findByUsername(username);
    if (user.getPassword().equals(password)) { // Line 45
        return user;
    }
    return null;
}
```

**7. Troubleshooting Steps Taken**:  
- List the actions you’ve already tried to resolve the issue and their outcomes.  
*Example*:  
  - Checked if `userRepository.findByUsername` returns null → Confirmed it does for valid usernames.  
  - Added debug logs to trace variable values → Found `user` is null.  
  - Reviewed documentation for `userRepository` → No issues found.

**8. Suspected Cause**:  
- Share your hypothesis about what’s causing the issue based on your investigation.  
*Example*: "The `userRepository.findByUsername` method might be failing to retrieve the user object, causing a null reference."

**9. Additional Context**:  
- Add any relevant details, such as screenshots, log files, or related tickets.  
- Attach files if applicable (e.g., stack trace, screenshot of error).  
*Example*: "Attached: `error_log.txt`, `login_page_screenshot.png`"

---

### Acceptance Criteria

- [ ] The issue is resolved, and the code performs the expected behavior.  
- [ ] The fix is tested in the specified environment (e.g., local development, unit tests).  
- [ ] The solution is documented in the ticket (e.g., what was changed and why).  
- [ ] (Optional) Code is reviewed by a peer or instructor.  
- [ ] No new issues are introduced by the fix.

---

### Comments Section (For Updates)

- Use this section to log progress, ask questions, or document feedback from peers/instructors.  
*Example*:  
  - "2025-05-04: Added null check to handle missing user. Testing now."  
  - "2025-05-04: Instructor feedback: Consider validating username input before querying."

---

### Tips for Students

1. **Be Specific**: Avoid vague descriptions like "it doesn’t work." Include error messages, line numbers, and observations.
2. **Use Screenshots/Logs**: Visuals help clarify complex issues. Attach them to the ticket.
3. **Document Everything**: Even failed attempts are valuable for learning and avoiding repeated work.
4. **Collaborate**: Use the Comments section to ask for help or share ideas with classmates.
5. **Keep it Concise**: Focus on relevant details to make the ticket easy to read.

---

### Example Jira Ticket

**Title**: NullPointerException in User Login Function  
**Type**: Bug  
**Priority**: High  
**Assignee**: Jane Doe  
**Labels**: `troubleshooting`, `java`, `authentication`  
**Components**: Backend  

**Description**:  
**Summary**: When a user tries to log in with valid credentials, the application crashes with a NullPointerException.  

**Steps to Reproduce**:  
1. Navigate to the login page.  
2. Enter username "testuser" and password "password123".  
3. Click "Login".  
4. Observe the crash.  

**Expected Behavior**: User is redirected to the dashboard.  
**Actual Behavior**: Application crashes with `NullPointerException at LoginService.java:45`.  

**Environment**:  
- Language: Java 17  
- Framework: Spring Boot 3.0  
- OS: macOS Ventura  
- Database: MySQL 8.0  

**Code Snippet**:  
```java
public User login(String username, String password) {
    User user = userRepository.findByUsername(username);
    if (user.getPassword().equals(password)) { // Line 45
        return user;
    }
    return null;
}
```

**Troubleshooting Steps**:  
- Verified `username` is not null.  
- Added debug log: `user` is null after `findByUsername`.  
- Checked database: User exists with correct username.  

**Suspected Cause**: `userRepository.findByUsername` is not fetching the user, possibly due to a database query issue.  

**Additional Context**: Attached `stacktrace.txt`.  

**Acceptance Criteria**:  
- [ ] Login works without crashing.  
- [ ] Fix is tested locally with valid and invalid credentials.  
- [ ] Solution is documented in the ticket.  



