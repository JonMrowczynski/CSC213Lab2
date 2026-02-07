We sometimes have commands that output a lot of text! Such as the command:

```
javac -verbose Lab2.java
```

If you want to save what is outputted to a file then you would issue:

```
> output.txt 2>&1
```

after the command where `> output.txt` means to write the contents of the command to a file named `output.txt`.
If this file already exists, then its contents are completely overwritten.

There are 2 streams when outputting text to a file:

1. The 1st stream is the **standard output**.
   - We can output to this stream by calling `System.out.println();`.
2. The 2nd stream is the **error stream**.
   - We can output to this stream by calling `System.err.println();`.

So `2>&1` is saying to redirect the 2nd output stream (the error stream) to the 1st stream (the standard output stream).

Effectively this merges the 2 outputs streams into the 1st output stream.

Therefore, the whole command:

```
javac -verbose Lab2.java > output.txt 2>&1
```

Will write **all the console output** from the command `javac -verbose Lab2.java` to a file named `output.txt`.