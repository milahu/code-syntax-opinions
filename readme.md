# milahu/code-syntax-opinions

code syntax opinions by milahu

i am somewhat opinionated when it comes to source code syntax

generally, changes to code should produce a "minimal diff"  
to make it easier to review code changes



## python



### complex function signatures

good:

```py
def some_function(
        some_argument_1,
        some_argument_2,
        some_argument_3,
        some_argument_4,
    ):
    return 1
```



## C languages



### preprocessor macros

good: preprocessor macros should have the same indent level as the C code

```c
    #if true
    printf("true\n");
    #else
    printf("false\n");
    #endif
```

bad: preprocessor macros should not have zero indent

```c
#if true
    printf("true\n");
#else
    printf("false\n");
#endif
```



### complex function signatures

good:

```c
int some_function(
    int argument_1,
    int argument_2,
    int argument_3,
)
{
    return 1;
}
```

bad: odd indents

this is bad because it creates lots of diff noise when renaming `some_function`

```c
int some_function(int argument_1,
                  int argument_2,
                  int argument_3,
)
{
    return 1;
}
```



### complex function calls

good:

```c
some_function(
    argument_1,
    argument_2,
    argument_3,
);
```

bad: odd indents

this is bad because it creates lots of diff noise when renaming `some_function`

```c
some_function(argument_1,
              argument_2,
              argument_3);
```



## markdown



### empty lines before headings

good: 3 empty lines before each heading

```md
# title

intro



## heading 1

section 1



### heading 1.1

section 1.1



## heading 2

section 2
```



### use hardbreaks instead of commas

commas are useful to compress text into a print format  
with as little print pages as possible

but for screen formats, this makes no sense  
and i prefer to render pauses as hardbreaks instead of commas

fullstops can be replaced by empty lines.  
fullstops are only needed to separate sentences  
in the same paragraph
