# byuctf writeups

Baby android 1

The challenge consists of an apk file and inorder to run it we need an android decompiler. We can use JADX which is an android decompiler.

We will upload our baby android 1 apk file and decompile it. It is advised to open the manifest file (xml file) first as it consists of all the activities. Now we will go to the main activity and understand what exactly is happening. Now from the main activity we can go to Utilities class.

In utilities class we can see the cleanup function. In the cleanup function the set text is missing. In order to find it we go to the xml file (resoucres → res → layout → xml). Now if we clearly analyze the xml file and arrange them in the decreasing order according to the margin_bottom layout . For this we can simply use our android studio and run our xml file and check it. And then we will get our flag

Flag - byuctf{android_piece_of_c4ke}

Baby android 2

The challenge consists of an apk file and inorder to run it we need an android decompiler. We can use JADX which is an android decompiler.

We will upload our baby android 2 apk file and decompile it. It is advised to open the manifest file (xml file) first as it consists of all the activities. Now we will go to the main activity and understand what exactly is happening. Now we can see that there is something called as flagchecker class in the main activity. If we go the flagchecker class we can find a library file named - “babyandroid”. Now we need to export the babyandroid file to convert it into binary file and now to open this binary file we use a decompiler called ghidra .

Now we will open ghidra and set it up. We will now open the file. Now we will see and understand what exactly is happening after taking the input from the user. We can see that a hardcoded . now we can write a python program to decode it and then we will get our flag.

Flag -  byuctf{c++_in_an_apk??}