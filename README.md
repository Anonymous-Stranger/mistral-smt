# mistral-smt
A clone of the [MISTRAL SMT solver](https://www.cs.utexas.edu/~tdillig/mistral/index.html) for fixing some bugs.


Mistal Constraint Solver
--------------------------------------------------------------------
Copyright (C) 2012 Isil Dillig, Thomas Dillig

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
--------------------------------------------------------------------


To compile, you need cmake installed on your system.

Then in the mistral folder:

mkdir build
cd build
cmake ..
make

After this, you can start the Mistral GUI as:

cd ui
../build/ui/mistral_ui

Important: The UI will only start from the /mistral/ui folder

If you want to use mistral as a library, read the file example/example.cpp
for how to link Mistral against your project.
