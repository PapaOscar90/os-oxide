# os-oxide
The operating system of rusticles.

The aim of the game, is to re-implement a bunch of Operating Systems assignments from unitversity, in a new oxidized language *Rust*. Each lab will be a seperate cargo workspace, to seperate each from eachother. We know most of these can be accomplished via crates, but will implement them using lower level rust. This is primarily a learning experience.

# Exercises

## Assignment 1
### Parser
Make a program that mimics a very minimal shell. The program must accept on its stdin a string
(optionally between quotes) and it should execute the corresponding command. The program must
search in the user’s standard search path (you can use the standard library function getenv()
and the environment variable PATH).

Note that you may only use the system calls fork() and (any variation of) exec() to make
processes and start executables. It is explicitly not allowed to use the standard library function

### IPC
Make a program that simulates a ring of communicating processes. The command accepts on its
stdin an integer, which denotes the number of processes in the ring (at least 1 and at most 16).
Each process communicates uni-directional (so, in one direction: read from the left neighbour, and
write to the right neighbour). The communication is started by the initial (oldest) process.

Each process receives from its left neighbour an integer, prints its relative process-id and the
number on the screen, increases the number by one, and sends the obtained number to its right
neighbour. When the value 50 has been reached, all processes should terminate. Make sure, that
no zombies processes remain. The relative process-id is defined as the relative position of the
process in the ring. The parent is number 0, the right neighbour is 1, and so on.

### File System
Make a program that traverses the file system tree starting from a folder that is given on stdin
(which can be relative to the folder the program is started in). The program should compare the
files it finds for equality, and print all unique pairs of files that have the same content. It should
print the paths of these files relative to the folder given as input. Do not worry about the order in
which you print these pairs, Themis will automatically sort the output before checking the result.
