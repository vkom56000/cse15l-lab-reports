# Part 1

 ## String Server Code

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String page = "";

    public String handleRequest(URI url) {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                    page = page + parameters[1] + "\n";
                    return String.format(page);
            }
            return "404 Not Found!";
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

![Image] https://github.com/vkom56000/cse15l-lab-reports/blob/main/lab2Example1.png 

The handleRequest method is called for the following screenshot. The method takes in a URL as its paramerter. The code then checks if the the url contains the /add-message path and if it does then it gets the query. It stores it in a string array and returns the requested string onto the website. There is also the page string to keep track of all the added messages. The page string is initially empty and as a new request to append a message is sent it handles it by adding it onto the page string. For this example the request was a string "Hi". So no values got changed because the message we wanted to add was a string and it got converted into a string. 

The HandleRequest method is called for the following screenshot. This method is the same as before and it also takes in a URL as its parameter. As shown in the example since the url contains a /add-message path it stores the request in a string array. The page string already has two requrests added onto it and it kept track of those strings. This time we passed in an integer value in the request however it is now a string. The value was able to be put into the string array parameters so it is now a string. 

# Part 2

## Failure Inducing input:
```
@Test
  public void testReverseInPlace4(){
    int [] input1 = {3,2,1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{1,2,3}, input1);
  }
```

## No Failure Inducing input:
```
@Test
  public void testReverseInPlace2(){
    int [] input1 = {2,2};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{2,2}, input1);
  }
```

## Symtom: 



## Before: 
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

## After: 
```
static void reverseInPlace(int [] arr){
    for(int i = 0; i < arr.length/2; i ++) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length-i-1] = temp;
    }
  }
```

The original program was traversing through the array and at each index i it would replace it with the value at the last index - i. However this is a problem because the original value at i would get lost. Since we want to reverse the array the original value is necessary for the array to be properly reversed. A better approach would be to swap both the index at i and the last index minus i. The new code correctly applies that concept. It only traverses half the number of times as the original code and each time it replces the index at i with the last index minus i and vice versa. This is accomplished by having a temporary variable to store the value of the index at i. 

# Part 3 

One thing I learned in week 2 and week 3 that I did not know before was how to host a web server. I do not fully understand the code required to start your own web server but I understand how to use the code provided for us such that I can create my own server take can in requests. I did not even know it was possible to create a webserver using java until now. I also learnt what the query part of a URL is and how it in a way makes a request to the backend of the server that is required to be handled. From looking at the code provided to us I realized that we can make a URLHandler class to handle all the requests made by the query part of the URL. This made me realize how the same thing is happening everytime I search things on google. The query part of the url is essentially making a request to the back end program that is handled in such a  way that it displays the correct information. In our server we used the query to append onto a string. Other servers would use the query in order to do more complicated things. This facinated me and I did some more research and found that there is a whole programing language dedicated to queries called SQL. One other thing that I learnt in week 3 was the definition of bugs and symptoms. I realized that there can be multiple symtoms from a single bug. Often times while testing my code it would fail for two different tests and I would incorrectly clasify that as two different bugs but I now realize that it is actually two different symtoms that result fromt he same bug. 
