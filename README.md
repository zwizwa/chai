chai
====

C / Haskell Abstract Interpretation

Using Language.C to build tools for C programming.

As a first problem, I'd like to find a bridge between FSMs and
RTOS-like tasks / coroutines.


Some elements:

 * C is a die-hard in the embedded programming world.  While a lot is
   possible using C as a compiler target for an exotic DSL, a new
   language is a serious barrier to entry. 

 * There is a sweet spot for C language extensions: constructs that
   can be implemented in C using run-time or macro support, but can
   also be translated at compile time using an external tool, able to
   perform transformations not possible using C or CPP alone.

 * C++ is too complicated to make this work.

 * Language.C is a great tool for analysis and re-synthesis of C code.

 * One of the major design questions for an embedded application is
   RTOS or FSMs?  What if they can be combined?

 * RTOS (Real Time Operating System) tasks or coroutines allow
   straightforward implementation of code behavior along the time
   dimension, a central problem in embedded systems.  (communication
   protocols, digital control, ...).  However, RTOS brings its own
   problems: memory overhead, resource contention, deadlock, ...

 * FSMs (Finite State Machines) are well suited for implementing
   event-driven / time-based systems, using a small memory footprint,
   and without complicating control flow as in an RTOS.  However, FSMs
   are a pain to write manually.  They are hard to implement in C
   without resorting to the singleton anti-pattern (i.e. managing a
   bunch of effectively global variables with unclear liveness).


