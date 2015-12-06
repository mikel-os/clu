# Core features

In order to keep features decoupled, modularity is a first class citizen. When you need a shell quickly working in a foreign OS, have to port _every_ feature is an obstacle.

Anyway, a minimal functionality is required always.

1. Get input.
2. Parse input as commands.
3. Execute "internal" programs.
4. Find "external" programs and execute them.
5. Execute "external" programs in background (as long the system allow that).
6. Support multiple commands in one line.
7. Interact respectfully with system services.\*
8. Transmit and detect errors.  
And of course...
9. Print prompt and errors.

\* Note that point must be done completely system per system. But it's important and MUST be done. Have in mind that can't affect to the portable code, so if that is the case, that code is not portable as intended. Sorry.

Every implementation of the shell needs this features at least.

>Note: pipes and I/O redirections are kept out of core features.
