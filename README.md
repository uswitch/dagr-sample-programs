Sample Dagr Programs
====================

[Dagr](https://github.com/uswitch/dagr) helps ensure programs run daily. It monitors a git repository (much like this sample one) and will attempt to run a `main` inside a directory (if one exists). Each directory represents a separate program.

Programs communicate to Dagr via `stderr` and `stdout`- output will be captured and stored on the dashboard and streamed to any connected web clients (via a websocket). Dagr uses the program's exit code to indicate whether the job succeeded or failed (`0` and `2` respectively). If a program exits with a code of `1` Dagr will attempt to re-execute the program after a configured delay: `1` represents a retryable error for an intermittent failure (perhaps a networking problem etc.).
