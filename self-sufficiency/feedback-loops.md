# Create your own feedback loops

One of my goals is also that my AI coding agent to be really self-sufficient in troubleshooting and development.

### Fundamentally design the software to be easy for an AI coding agent to directly interact and rapidly troubleshoot
- Create your own feedback loops so you're as self-sufficient as possible in making this happen without my intervention
- What implementation decisions would make the AI easily be able to run it, test it, understand what's happening, and troubleshoot itself? 
- How do I avoid spending a lot of time screenshotting things for the AI coding agent, and empower it to close its own loop? 
- The logs should be clearly accessible to the AI coding agent as it's running so it has a clear picture of what's happening as I use it.

### Do everything you can so I don't have to spend my days taking screenshots and feeding them to the AI coding agent (at least as little as possible)
- If there's anything that would require a manual screenshot to troubleshoot, make sure that everything else that could have been logged and observed directly by the AI coding agent has been observed in logs, api endpoints, health check endpoints, curl-testable endpoints, and the like. 
- That way, if a screenshot is necessary, it's very clear why and what to look for and isolated the likely issue, since everything else has been already checked and validated.
- If nonetheless a manual screenshot is unfortunately the only unavoidable way to close the feedback loop, make sure that error messages give all the info required for the ai coding agent to quickly understand (e.g. expand to show details)

### Automated browser testing
* The AI coding agent might have access to operate a Chrome browser.
	- Definitely check out the capabilities. For Cursor it's https://cursor.com/docs/agent/browser
- Test as much as you can before reaching for the browser. Ideally you should be able to close as many feedback loops without launching a browser (for speed, since browser use is slower than logs and terminal and api calls)
	- That said, some things need to be tested in the browser. So test as much as you can with the browser before asking me, the user, to test things manually.
- Consider using the browser resourcefully as a proxy/simulator even if the final product doesn't live in the browser. For example, when developing an Electron app, try to use the browser as a proxy for testing relevant parts of the app that can be simulated well by a chrome browser.

