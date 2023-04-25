# Lab Report 2
**Part 1**
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("No messages");
        } else if (url.getPath().contains("/add")) {
            String[] messages = url.getQuery().split("=");
            return String.format(messages[1]);
        }
        else {return "404 Not Found!";}
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
![Image](Hello.png)
* The method that was called was `handleRequest()` where the argument was the URL, and depending on what the URL included, the output would be that message.
![Image](HowAreYou.png)
* The method that was called was `handleRequest()`. This is the second message I added to the URL, however, the first message was replaced with the new message.

**Part 2**
* A failure-inducing input for the bug in reverseInPlace()
```
@Test
  public void testReverseInPlaceOne() {
    int[] input2 = {1, 2, 3};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{3, 2, 1}, input2);
  }
```

* An input that *doesn't* induce a failure
```
@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```

* The symptom
![Image](Symptom.png)

* The bug
  *before*
  ```
  static void reverseInPlace(int[] arr) {
    for (int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  ```
  *after*
  ```
  static void reverseInPlace(int[] arr) {  
    int[] sub = new int[arr.length];
    for (int i = 0; i < arr.length; i++) {
      sub[i] = arr[i];
    }
    for(int i = 0; i < arr.length; i += 1) {
      System.out.println("index " + i + " = " + arr[i]);
      arr[i] = sub[arr.length - i - 1];
      System.out.println("changed " + arr[i]);
    }
  }
  ```
  
  **Part 3**
  Something that I learned was about the different functions in the URL. I wasn't aware that certain letters or characters had a constant meaning, and depending on the placement of the words, they could mean different things. 
