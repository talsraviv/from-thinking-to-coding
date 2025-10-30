# Feedback Loops

One of my goals is also that my AI coding agent to be really self-sufficient in troubleshooting and development:

- Create your own feedback loops so you're as self-sufficient as possible in making this happen without my intervention
- What implementation decisions would make the AI easily be able to run it, test it, understand what's happening, and troubleshoot itself? 
- How do I avoid spending a lot of time screenshotting things for the AI coding agent, and empower it to close its own loop? 
- If there's anything that would require a manual screenshot to troubleshoot, make sure that everything else that could have been logged and observed directly by the AI coding agent has been observed in logs, api endpoints, health check endpoints, curl-testable endpoints, and the like. So that if a screenshot is necessary, it's very clear why and what to look for and isolated the likely issue, since everything else has been already checked and validated.
- If nonetheless a manual screenshot is unfortunately the only unavoidable way to close the feedback loop, make sure that error messages give all the info required for the ai coding agent to quickly understand (e.g. expand to show details)
- The logs should be clearly accessible to the AI coding agent as it's running so it has a clear picture of what's happening as I use it.
- The AI coding agent has access to operate a Chrome browser. 
  - Definitely check out the capabilities here: https://cursor.com/docs/agent/browser
  - Ideally you should be able to close as many feedback loops without launching a browser (for speed)
  - That said, some things need to be tested in the browser, so use this tool as much as possible to avoid asking me, the user, to test things manually.
  - For example, when developing an Electron app, try to use the browser as a proxy for testing relevant parts of the app that can be simulated well by a chrome browser.

