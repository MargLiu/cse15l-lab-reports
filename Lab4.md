#Lab 4

##Step 5
![Image](Step5.png)
```
git clone https://github.com/MargLiu/lab7
cd lab7
```

##Step 6
![Image](Step6.png)
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```

##Step 7 & Step 8
![Image](Step7+8.png)
```
vim ListExamples.java
/while(index2 [enter]
jjes2 [esc]
:wq!
```

```
<up> <up>
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
<up> <up>
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```

##step 9
![Image](Step9.png)
```
git add *.class
git commit -m 'update'
git push https://github.com/MargLiu/lab
```
