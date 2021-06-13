# Alternate Data Streams (ADS)

### This creates an empty file called test.txt, while simultaneously creating a hidden file called hidden.txt. 
```C:\>echo "Super secret info" > test.txt:hidden.txt```

### To view the secret message.
```C:\>notepad.exe test.txt:hidden.txt```
