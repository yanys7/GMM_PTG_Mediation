# This is a general project template that contains "set_env.sh" to set
# environment variables, "/src" and "/frame" to separate source and
# template files, "/include" to accomondate headers and prototypes.
# There is a toy vector add implemented with STL and C++ templates.
# There is also a toy Cmake file for beginner to get started.

# To compile, follow the these instructions.

>> source set_env.sh
>> mkdir build
>> cd build
>> cmake ..
>> make

# To run the program.

>> cd bin
>> ./helloworld.x

# To create your own project.
#
# 1. Modify PROJECT_NAME from HELLOWORLD to your own project name in set_env.sh
# 2. Write source files (.cpp) in /src, templates (.hpp or .hxx) in /frame.
# 3. Put headers and prototypes (.h or .hpp) in /include.
# 4. Write additional test files (.cpp with main() function) in /test.
# 5. Follow the 5 instructions above to compile.

# Port the new project with git.

>> rm -rf .git
>> git init
>> git commit -m "first commit of the new project"
