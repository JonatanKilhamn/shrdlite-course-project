The Shrdlite course project
============================

Shrdlite is a programming project in Artificial Intelligence, a course given 
at the University of Gothenburg and Chalmers University of Technology.
For more information, see the course webpages:

- <http://ChalmersGU-AI-course.github.io/>

The goal of the project is to create an interpreter and a planner so that
a person can control a robot in a blocks world to move around objects,
by giving commands in natural language.

To make the project more interesting, there is a web-based graphical 
interface from which the user can interact with the blocks world.

The interface is written in TypeScript (which compiles into Javascript),
and it can be run in two different modes:

- as a HTML web application, using SVG animations for displaying the world

- as an offline text application, where input is provided at the command line
  (requires that Node.JS is installed, but nothing of the terminal)

To be able to run the system you need to install Node.JS and TypeScript.
Do that. Now.

### What is already implemented and what is missing

The natural language parser is already implemented using the 
[Nearley parsing library](https://github.com/Hardmath123/nearley).

Furthermore, there are two different implementations of the blocks world:
the SVGWorld and the TextWorld.

What is not implemented correctly is the natural language interpreter
and the robot planner. What you are given are stubs that return
a dummy interpretation and a dummy plan respectively. Your goal is to implement
the interpreter and the planner so that the robot behaves as it should.

Furthermore, there is an initial implementation of weighted graphs in `Graph.ts`.

### About TypeScript

TypeScript is a typed superset of Javascript that compiles to plain Javascript.
It is open-source and not specific to any browser or operating system.

For information about the language, please visit the official site:

- <http://www.typescriptlang.org/>

More detailed information
--------------------------

There is a Makefile if you want to use the GNU Make system. Here's what it can do:

- `make clean`: Removes all auto-generated Javascript files
- `make all`: Calls TypeScript for all targets
- `make shrdlite-html.js`, `make shrdlite-offline.js` etc.:
  Calls TypeScript for the given target,
  i.e., it compiles the file `shrdlite-X.ts` into `shrdlite-X.js`

### Data structures

You probably want to use some kind of collection datatype (such as a heap
and/or priority queue), and we suggest the following library:

- [typescript-collections](https://github.com/basarat/typescript-collections)

In fact, you have to use this library anyway (in Graph.ts) and it's
already included in the `lib` directory.

### Using JavaScript modules in TypeScript

If you want to use standard JavaScript libraries in TypeScript, you have to
add a TypeScript declaration file for that library. 
The [DefinitelyTyped library](https://github.com/borisyankov/DefinitelyTyped)
contains declaration files for several libraries, such as the following two:

- `node.d.ts`
- `jquery.d.ts`

In fact, they are already included in the `lib` directory.

### JavaScript chart parser

The parser is generated by [Nearley](http://github.com/Hardmath123/nearley).
The grammar is in the file `grammar.ne`, and it is compiled into the 
Javascript file `grammar.js`. You don't have to install Nearley if you 
don't plan to make any changes in the grammar.


List of files
--------------

BSD Makefile for automatically creating `.js` files from `.ts` files:
- `Makefile`

Main browser files:
- `shrdlite.html`, `shrdlite.css`

Wrapper file for the browser-based interface:
- `shrdlite-html.ts`

Wrapper file for the Node.JS-based interface:
- `shrdlite-offline.ts`

Main TypeScript module:
- `Shrdlite.ts`

TypeScript interfaces and classes for the different implementations of the blocks world:
- `World.ts`, `SVGWorld.ts`, `TextWorld.ts`, `ExampleWorlds.ts`

TypeScript modules for parsing, interpretation and planning:
- `Parser.ts`, `Interpreter.ts`, `Planner.ts`

TypeScript module for weighted graphs:
- `Graph.ts`

Grammar files used by the Nearley chartparser:
- `grammar.js`, `grammar.ne`

External TypeScript libraries:
- `lib/collections.ts`

TypeScript declaration files for non-TypeScript libraries:
- `lib/jquery.d.ts`, `lib/node.d.ts`

External Javascript libraries:
- `lib/jquery-1.11.0.min.js`, `lib/nearley.js`

