# Command Line Lightweight Utility

A simple shell for Linux and Plan 9 written on C.

## Motivation

* I need a shell easy to modify, to make it work with (and without) a special system API on Linux.
* As that API is related with Plan 9, it would be convenient work there too with the same shell.
* "Luckily" the shell in that system (_rc_) lacks of some features, making work on Plan 9 a little more frustrating than needed.
* I need this working as soon as possible (_I'm late! I'm late!_).

## Description

So to overcome this problematic and reuse the solution as much I can with the same effort, I decided wrote a **simple** and **decoupled** program...

* ... which can be adapted to other spartan systems quickly.
* ... where most features can be modified (or disabled for compilation) easily.

## License

>Command Line Lightweight Utility - A simple shell for Linux and Plan 9.  
Copyright &copy; 2015 Mikel Cazorla Pérez

>This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; version 2 of the License only.

>This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

>You should have received a copy of the GNU General Public License along
with this program; if not, write to the Free Software Foundation, Inc.,
51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.
