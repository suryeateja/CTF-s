# byuctf writeups

Baby android 1

The challenge consists of an apk file and inorder to decompile it we need an android decompiler. We can use JADX which is an android decompiler.

We will upload our baby android 1 apk file and decompile it. It is advised to open the manifest file (xml file) first as it consists of all the activities. Now we will go to the main activity and understand what exactly is happening. We can see that a new object for the utilities class is being created and cleanup function is being called for that object. in order to check what exactly is happening inside the cleanup function we move from the main activity  to Utilities class.

In utilities class we can see the cleanup function. In the cleanup function the set text is missing. In order to find it we go to the xml file (resoucres → res → layout → xml). Now if we clearly analyze the xml file and arrange them in the decreasing order according to the margin_bottom layout values or For we can simply use our android studio and run our xml file and check it. And then we will get our flag.

![image.png](image.png)

the above image is the flag we recieve when we use android studio to run our xml file.

Flag - byuctf{android_piece_of_c4ke}

Baby android 2

The challenge consists of an apk file and inorder to decompile it we need an android decompiler. We can use JADX which is an android decompiler.

We will upload our baby android 2 apk file and decompile it. It is advised to open the manifest file (xml file) first as it consists of all the activities. Now we will go to the main activity and understand what exactly is happening. We can see that there is checker function.Now we can see that there is something called as flagchecker class in the main activity. If we go the flagchecker class we can find a function loadlibrary is being called for “babyandroid”.

now in order to check the file and debug it we need to go the resouce library(resources —> lib) and search for the file . Now we need to export the babyandroid file which is a binary file and now to open this binary file we use a decompiler called ghidra .

Now we will open ghidra and set it up. We will now open the file. Now we will see and understand what exactly is happening after taking the input from the user.

```c

  if (lVar2 == 0x17) {
    for (local_58 = 0; local_58 < 0x17; local_58 = local_58 + 1) {
      pcVar1 = (char *)FUN_00120710(local_28,(long)local_58);
      if (*pcVar1 != "bycnu)_aacGly~}tt+?=<_ML?f^i_vETkG+b{nDJrVp6=)="[(local_58 * local_58) % 0x 2f]
         ) {
        local_29 = 0;
        goto LAB_00120608;
      }
    }
    local_29 = 1;
  }
  else {
    local_29 = 0;
  }
```

 the first thing is to understand the above code. in the above code we can check that the hardcoded value - “bycnu)_aacGly~}tt+?=<_ML?f^i_vETkG+b{nDJrVp6=)=” . now we will convert the above code into a simple python program and run it . and then we will get our flag 

```python
reference = "bycnu)_aacGly~}tt+?=<_ML?f^i_vETkG+b{nDJrVp6=)"
length = 23  # 0x17 in decimal
output = ""

for i in range(length):
    index = (i * i) % 47
    output += reference[index]

print("Valid input string is:", output)

```

Flag -  byuctf{c++_in_an_apk??}