# HELL SHELL

Embed the C code in your shell scripts

This is not a C interpreter but something like that

### REQUIRES

**clang**

### INSTALL

Put hellshell to /usr/local/bin

### USAGE
```
USAGE: hellshell [command] or [FILE]
Or define hellshell in the first line of the script: #!/usr/bin/env hellshell
COMMANDS
	create new_script_name	create example script
	cleanup			delete cache folder
```

### EXAMPLE

```bash
#!/usr/bin/env hellshell
#SHELL sh <-- can be any shell like bash or zsh

echo "Example 1:"

#CSTART
// This C code block will be run here
#include <stdio.h>
int main()
{
  printf("Hello from C\n");
  return 0;
}
#CEND

echo "Example 2:"

#CFSTART c_function_name
// This C code will be run when c_function_name is called in a script
#include <stdio.h>
int main(int argc, char *argv[])
{
  if(argc == 2) printf("%s\n", argv[1]);
  return 0;
}
#CFEND

c_function_name "Yo! From hellshell to C"

echo "Long time only first run"

```
### TESTED

- Ubuntu
- CentOS
- macOS
- FreeBSD
- OpenBSD
