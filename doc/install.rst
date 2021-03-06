.. highlight:: bash

.. _install:

Compiling mpi from source
===============================


Installation steps
------------------

#. Download the source code of the latest stable version by cloning the ``TRIQS/mpi`` repository from GitHub::

     $ git clone https://github.com/TRIQS/mpi mpi.src

#. Make sure that all additional dependencies are installed on your system and available in your environment.
   Alternatively build the dependencies from source instead with::

     $ (cd deps && ./download.sh)

   In this case they will be installed together with your application.

#. Make sure that all additional dependencies are installed on your system and available in your environment.
   Alternatively build the dependencies from source instead with::

     $ (cd deps && ./download.sh)

   In this case they will be installed together with your application.

#. Create and move to a new directory where you will compile the code::

     $ mkdir mpi.build && cd mpi.build

#. In the build directory call cmake, including any additional custom CMake options, see below::

     $ cmake -DCMAKE_INSTALL_PREFIX=path_to_install_dir ../mpi.src

#. Compile the code, run the tests and install the application::

     $ make
     $ make test
     $ make install

Versions
--------

To use a particular version, go into the directory with the sources, and look at all available versions::

     $ cd mpi.src && git tag

Checkout the version of the code that you want::

     $ git checkout 2.1.0

and follow steps 2 to 4 above to compile the code.

Custom CMake options
--------------------

The compilation of ``mpi`` can be configured using CMake-options::

    cmake ../mpi.src -DOPTION1=value1 -DOPTION2=value2 ... ../mpi.src

+-----------------------------------------------------------------+-----------------------------------------------+
| Options                                                         | Syntax                                        |
+=================================================================+===============================================+
| Specify an installation path other than path_to_triqs           | -DCMAKE_INSTALL_PREFIX=path_to_mpi      |
+-----------------------------------------------------------------+-----------------------------------------------+
| Build in Debugging Mode                                         | -DCMAKE_BUILD_TYPE=Debug                      |
+-----------------------------------------------------------------+-----------------------------------------------+
| Disable testing (not recommended)                               | -DBuild_Tests=OFF                             |
+-----------------------------------------------------------------+-----------------------------------------------+
| Build the documentation                                         | -DBuild_Documentation=ON                      |
+-----------------------------------------------------------------+-----------------------------------------------+
