# angr

_learning how to use angr effectively._

## CLE (CLE loads everything): the loader
- `proj.loader`
- Converts binary file to representation in virtual address space
- Used to
  - See the shared libraries loaded alongside your program

## `project.factory`
- A more user-friendly interface for instantiating `angr` classes that otherwise require a reference to the project.

### blocks: `project.factory.block(vaddr)`
- **angr analyzes code in units of _basic blocks_**

### states: `SimState`
- the **project** is just the "initialization image" of the program
- performing execution with angr is done on simulated program states, called **`SimState`**s
- `SimState`s are treated as **immutable** by simulation (stepping forward in simulation creates new `SimState`s, rather than modifying them)
- `SimState`s contain
  - program memory (`state.mem`)
  - registers (`state.regs`)
  - filesystem data

### simulation managers (`project.factory.simulation_manager(state)`)
- the primary interface for performing simulations (i.e. actually executing code)

## analyses

---

## useful functions

### blocks
- `block.pp()`. pretty-print the disassembly of the basic block
- `block.instructions`. the number of instructions in the basic block

### states

### simulation managers
- `simgr.active`. list of active states (called the active **stash**)
- 

### bitvectors
- `bv.length`. get the length of the bitvector
- `state.solver.BVV(value, length)` (bitvector value). create a bitvector
- `state.solver.eval(bv)`. convert bitvector to python int

---

## acronyms
- **CLE**. CLE Loads Everything
- **CFG**. control-flow graph

