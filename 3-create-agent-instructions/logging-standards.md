# Structured Logging with Timestamps

All logging should include timestamps for easy session identification:
- Format: `[HH:MM:SS] [PREFIX] message`
- Makes it easy to identify fresh terminal sessions
- Helps track performance and timing
- Essential for debugging async operations

Implement consistently across all files (main process, services, renderer, preload).

