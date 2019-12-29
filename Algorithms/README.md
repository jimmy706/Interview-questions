# Algorithm interview questions

### Q1: How do you find the missing number in a given integer array of 1 to 100? 
> Difficulty : ⭐⭐

```javascript
function findMissingNum(arr, actualLength){
  let arrSet = new Set(arr);
  let missingCount = actualLength - arr.length;
  for(let i = 1; i <= actualLength && missingCount > 0; i++){
    if(!arrSet.has(i)){
      console.log(i);
      missingCount--;
    }
  }
}
```
**🔗Source:** https://javarevisited.blogspot.com/2014/11/how-to-find-missing-number-on-integer-array-java.html

### Q2: How do you find the largest and smallest number in an unsorted integer array?
> Difficulty : ⭐⭐

```javascript
function findMinAndMax(arr){
    let min = Number.MAX_VALUE;
    let max = Number.MIN_VALUE;
    for(num of arr){
        if(num < min){
            min = num;
        }
        if(num > max){
            max = num;
        }
    }
    console.log({min,max});
}
```
**🔗Source:** https://www.java67.com/2014/02/how-to-find-largest-and-smallest-number-array-in-java.html

### Q3: How do you find all pairs of an integer array whose sum is equal to a given number?
> Difficulty : ⭐⭐⭐

```javascript
function findPairs(arr, val){
  let arrSet = new Set(arr);
  for(num of arr){
    let otherNum = val - num;
    if(arrSet.has(otherNum)){
      console.log([num,otherNum]);
    }
  }
}
```
**🔗Source:** https://javarevisited.blogspot.com/2014/08/how-to-find-all-pairs-in-array-of-integers-whose-sum-equal-given-number-java.html

### Q4: Find first non repeated character in a String 
> Difficulty : ⭐⭐⭐

```javascript
function findFirstNonRepeatedChar(str){
  let chars = [...str];
  let tempArr = chars.reduce((obj,char)=>{
    if(obj[char]){
      obj[char]++;
    }
    else{
      obj[char] =1;
    }
    return obj;
  },{});
  for(key in tempArr){
    if(tempArr[key] == 1){
      return key;
    }
  }
  return null;
}
```
**🔗Source:** https://javarevisited.blogspot.com/2014/03/3-ways-to-find-first-non-repeated-character-String-programming-problem.html

### Q5: How is an integer array sorted in place using the quicksort algorithm?
> Difficulty : ⭐⭐⭐⭐⭐

```java
    private static int partition(int arr[],int left, int right){
        int pivot = arr[left + (right - left) / 2]; // TODO: pivot is middle index
        int low = left, high = right;
        while(low <= high){
            while(arr[low] < pivot) low++;
            while(arr[high] > pivot) high--;
            if(low <= high){
                swap(arr,low,high);
                low++;
                high--;
            }
        }
        return low;
    }

    private static void swap(int arr[], int i, int j){
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    private static void quicksort(int arr[], int start, int end){
        int i = partition(arr,start,end);
        if(start < i - 1){
            quicksort(arr,start, i - 1);
        }
        if(end > i){
            quicksort(arr,i,end);
        }
    }
```
**🔗Source:** https://javarevisited.blogspot.com/2014/08/quicksort-sorting-algorithm-in-java-in-place-example.html

### Q6: How do you reverse an array?
> Difficulty : ⭐⭐

```javascript
function reverseArr(arr){
  let left = 0, right = arr.length - 1;
  while(left <= right){
    let temp = arr[left];
    arr[left] = arr[right];
    arr[right] = temp;
    left++;
    right--;
  }
  return arr;
}
```
**🔗Source:** https://javarevisited.blogspot.com/2013/03/how-to-reverse-array-in-java-int-String-array-example.html

### Q7: Write a function that calculate the Fibonacci number
> Difficulty : ⭐⭐

```javascript
function fibonacci(num){
  if(num < 2) return num;
  else {
    return fibonacci(num - 1) + fibonacci(num - 2);
  }
}
```
### Q7: Implement a LinkedList
> Difficulty : ⭐⭐

```java
public class Node {
    private Node next;
    private int data;

    public Node(int data){
        this.data = data;
        this.next = null;
    }


    public Node getNext() {
        return next;
    }

    public void setNext(Node next) {
        this.next = next;
    }

    public int getData() {
        return data;
    }

    public void setData(int data) {
        this.data = data;
    }
}

public class LinkedList {
    private Node head;
    private Node tail;

    public LinkedList(){
        this.head = this.tail = null;
    }

    public void addNode(int data){
        if(this.tail == null){
            this.head = this.tail = new Node(data);
        }
        else{
            Node newNode = new Node(data);
            this.tail.setNext(newNode);
            this.tail = newNode;
        }
    }

    public Node getHead() {
        return head;
    }

    public void setHead(Node head) {
        this.head = head;
    }

    public Node getTail() {
        return tail;
    }

    public void setTail(Node tail) {
        this.tail = tail;
    }

    public int getSize(){
        Node current = this.head;
        int count = 0;
        while(current != null){
            count++;
            current = current.getNext();
        }
        return count;
    }

}
```

### Q8: How to reverse a LinkedList?
> Difficulty : ⭐⭐⭐⭐⭐

```java
public void reverse(){
        if(getSize() > 2){
            Node current = this.head.getNext();
            Node prev = this.head;
            Node next = current.getNext();
            current.setNext(prev);
            this.head.setNext(null);
            while(next != this.tail){
                prev = current;
                current = next;
                next = next.getNext();
                current.setNext(prev);
            }
            this.tail.setNext(current);
            Node temp = this.head;
            this.head = this.tail;
            this.tail = temp;
        }
        else if(getSize() == 2){
            this.head.setNext(null);
            this.tail.setNext(this.head);
            Node temp = this.head;
            this.head = this.tail;
            this.tail = temp;
        }
    }
```
**🔗Source:** https://www.java67.com/2016/07/how-to-reverse-singly-linked-list-in-java-example.html

### Q9: Remove duplicates from an unsorted LinkedList
> Difficulty : ⭐⭐⭐

```java
public void removeDuplicated(){
        Set<Integer> dataSet = new HashSet<>();
        Node current = this.head;
        Node prev = null;
        while(current != null){
            Integer data = current.getData();
            if(!dataSet.contains(data)){
                dataSet.add(data);
                prev = current;
            }
            else{
                // Remove duplicated
                if(current == this.tail){
                    prev.setNext(this.tail.getNext());
                    this.tail = prev;
                }
                else{
                    prev.setNext(current.getNext());
                }
            }
            current = current.getNext();
        }
    }
```
**🔗Source:** https://www.geeksforgeeks.org/remove-duplicates-from-an-unsorted-linked-list/

### Q10: How to find the third node from the end (tail) of LinkedList in one pass?
> Difficulty : ⭐⭐⭐⭐

```java
// Implement a "tortoise and hare" algorithm
public Node getNodeFromTail(int pos){
        if(pos < 1 || pos > getSize()){
            return null;
        }
        Node fast = head; Node slow = head;
        int start = 1;
        while(fast.getNext() != null){
            fast = fast.getNext();
            start++;
            if(start > pos){
                slow = slow.getNext();
            }
        }
        return slow;
    }
```
**🔗Source:** https://javarevisited.blogspot.com/2016/07/how-to-find-3rd-element-from-end-in-linked-list-java.html

### Q11: How do you check if two strings are anagrams of each other?
> Difficulty : ⭐⭐⭐

```javascript
function isAnagrams(s1, s2){
  if(s1.length !== s2.length){
    return false;
  }
  let charsFromS1 = [...s1];
  let charsFromS2 = [...s2];
  charsFromS1 = charsFromS1.sort();
  charsFromS2 = charsFromS2.sort();
  for(let i = 0; i < charsFromS1.length; i++){
    if(charsFromS1[i] !== charsFromS2[i]){
      return false;
    }
  }
  return true;
}
```
**🔗Source:** https://javarevisited.blogspot.com/2013/03/Anagram-how-to-check-if-two-string-are-anagrams-example-tutorial.html

### Q12: How do you check if a given string is a palindrome?
> Difficulty : ⭐⭐⭐

```java
boolean isPalindromes(String str){
        str = str.toLowerCase();
        for(int i = 0; i < str.length()/2; i++){
            if(str.charAt(i) != str.charAt(str.length() - i - 1)){
                return false;
            }
        }
        return true;
    }
```
**🔗Source:** https://www.java67.com/2015/06/how-to-check-is-string-is-palindrome-in.html

### Q13: How do you reverse a string using recursion?
> Difficulty : ⭐⭐⭐

```javascript
function reverse(str){
  if(str === null || str.length === 0){
    return str;
  }
  return str.charAt(str.length - 1) + reverse(str.substr(0,str.length - 1));
}
```

### Q14: Write a function that calculate factorial number?
> Difficulty : ⭐⭐

```javascript
function factorial(n){
  if(n === 0){
    return 1;
  }
  else return n * factorial(n - 1);
}
```
**🔗Source:** https://en.wikipedia.org/wiki/Factorial

### Q15: Write a function to print all permutations of a string?
> Difficulty : ⭐⭐⭐⭐⭐

```javascript
function findPermutations(str){
  const charsFromStr = [...str];
  let countMap = new Map();
  for(let c of charsFromStr){
    if(countMap.has(c)){
      countMap.set(c,countMap.get(c) + 1);
    }
    else{
      countMap.set(c, 1);
    }
  }

  let result = new Array(str.length);
  permuteUtils(countMap,result,0);
}

function permuteUtils(countMap, result, level){
  if(level === result.length){
    let str = result.join('');
    console.log(str);
    return;
  }
  for(let [char,count] of countMap){
    if(count === 0){
      continue;
    }
    result[level] = char;
    countMap.set(char,--count);
    permuteUtils(countMap, result, level + 1);
    countMap.set(char,++count);
  }
}
```
**🔗Source:** https://www.youtube.com/watch?v=nYFd7VHKyWQ&t=1153s

### Q16: Implement Binary Search Tree data structure?
> Difficulty : ⭐⭐⭐

```java
class Node<T> {
    private T data;
    private Node<T> left, right;

    public Node(T data){
        this.data = data;
        this.left = this.right = null;
    }

    public boolean isLeaf(){
        return (this.left == null) && (this.right == null);
    }

    public T getData(){
        return this.data;
    }

    public void setData(T data){
        this.data = data;
    }

    public Node getLeft(){
        return this.left;
    }

    public Node getRight(){
        return this.right;
    }

    public void setLeft(Node<T> node){
        this.left = node;
    }

    public void setRight(Node<T> node){
        this.right = node;
    }

    @Override
    public String toString() {
        return "Node{" +
                "data=" + data +
                '}';
    }
}

class BinarySearchTree<T extends Comparable<T>> {
    private Node<T> root;

    public BinarySearchTree(){
        this.root = null;
    }

    public void insert(T data){
        root = insertRec(root,data);
    }

    private Node insertRec(Node<T> node,T data){
        if(node == null){
            return new Node<>(data);
        }
        else if(data.compareTo(node.getData()) < 0){
            node.setLeft(insertRec(node.getLeft(),data));
        }
        else if(data.compareTo(node.getData()) > 0){
            node.setRight(insertRec(node.getRight(),data));
        }
        return node;
    }

}
```
**🔗Source:** https://www.baeldung.com/java-binary-trees

### Q17: How do you perform preorder traversal in a given BNS tree?
> Difficulty : ⭐⭐⭐

```java
void preOrder(Node node){
    //root -> left -> right
    System.out.println(node.getData());
    if(node.getLeft() != null){
        preOrder(node.getLeft());
    }
    if(node.getRight() != null){
        preOrder(node.getRight());
    }
}
```

### Q18: How do you perform an inorder traversal in a given BNS tree?
> Difficulty : ⭐⭐⭐

```java
void inOrder(Node node){
    // left -> root -> right
    if(node.getLeft() != null){
        inOrder(node.getLeft());
    }
    System.out.println(node.getData());
    if(node.getRight() != null){
        inOrder(node.getRight());
    }
}
```

### Q19: How do you implement a postorder traversal algorithm in BNS Tree?
> Difficulty : ⭐⭐⭐

```java
void postOrder(Node node){
    // left -> right -> root
    if(node.getLeft() != null){
        postOrder(node.getLeft());
    }
    if(node.getRight() != null){
        postOrder(node.getRight());
    }
    System.out.println(node.getData());
}
```

### Q20: How do you calculate number of Node in BNS Tree?
> Difficulty : ⭐⭐⭐

```java
public int size(){
    return countNode(root);
}

private int countNode(Node node){
    if(node != null){
        return (1 + countNode(node.getLeft()) + countNode(node.getRight()));
    }
    else{
        return 0;
    }
}
```

### Q21: How do you search item from BNS Tree?
> Difficulty : ⭐⭐⭐

```java
public Node<T> search(T data){
    return searchRec(root,data);
}

private Node<T> searchRec(Node<T> node, T data){
    if(node == null){
        return null;
    }
    else if(data.compareTo(node.getData()) == 0){
        return node;
    }
    else if(data.compareTo(node.getData()) < 0){
        return searchRec(node.getLeft(),data);
    }
    else{
        return searchRec(node.getRight(),data);
    }
}
```

### Q22: How to swap 2 numbers without using temp or third variable?
> Difficulty : ⭐⭐⭐

```javascript
function swap(arr, i, j){
    arr[i] = arr[i] + arr[j];
    arr[j] = arr[i] - arr[j];
    arr[i] = arr[i] - arr[j];
}
```
**🔗Source:** https://javarevisited.blogspot.com/2013/02/swap-two-numbers-without-third-temp-variable-java-program-example-tutorial.html

### Q23: Implement a bubble sort algorithm?
> Difficulty : ⭐⭐

```javascript
function bubbleSort(arr){
  for(let i = 0; i < arr.length - 1; i++){
    for(let j = i + 1; j < arr.length; j++){
      if(arr[i] > arr[j]){
        arr[i] = arr[i] + arr[j];
        arr[j] = arr[i] - arr[j];
        arr[i] = arr[i] - arr[j];
      }
    }
  }
  return arr;
}
```

### Q24: How do you implement an insertion sort algorithm?
> Difficulty : ⭐⭐⭐

```javascript
function insertSort(arr){
  for(let i = 1; i < arr.length; i++){
    let j = i;
    while(j >= 1){
      if(arr[j] < arr[j - 1]){
        let temp = arr[j - 1];
        arr[j - 1] = arr[j];
        arr[j] = temp;
      }
      j--;
    }
  }
  return arr;
}
```

### Q25: How is a merge sort algorithm implemented?
> Difficulty : ⭐⭐⭐⭐⭐

```javascript
function mergeSort(arr, start, end){
  if(start < end){
    let middle = Math.floor((start + end) / 2);
    mergeSort(arr,start,middle);
    mergeSort(arr,middle + 1, end);
    merge(arr,start,middle,end);
  }
}

function merge(arr,start, middle, end){
  let length = end - start + 1;
  let tempArr = new Array(length);
  let i = start; // Travel from start -> mid
  let j = middle + 1; // Travel from mid + 1 -> end
  let k = 0; // index of tempArr

  // Travel in both sign and add smaller elements to tempArr
  while(i <= middle && j <= end){
    if(arr[i] <= arr[j]){
      // Add smaller element to tempArr
      tempArr[k] = arr[i];
      k++; i++;
    }
    else{
      tempArr[k] = arr[j];
      k++; j++;
    }
  }

  // Check for sure all elements have loop throught
  while(i <= middle){
    tempArr[k] = arr[i];
    k++; i++;
  }
  while(j <= end){
    tempArr[k] = arr[j];
    k++; j++;
  }

  // Merge tempArr to original one
  i = start;
  for(k = 0; k < length; k++){
    arr[i] = tempArr[k];
    i++;
  }
}
```
**🔗Source:** https://www.interviewbit.com/tutorial/merge-sort-algorithm/

### Q26: How do you implement a counting sort algorithm?
> Difficulty : ⭐⭐⭐

```javascript
// NOTE: This algorithm work best on really small number array
function countingSort(arr){
  let count = new Array(100);

  for(let i = 0; i < count.length; i++){
    count[i] = 0;
  }

  for(let num of arr){
    count[num]++;
  }

  for(let i = 1; i < count.length; i++){
    count[i] += count[i - 1];
  }

  let sortedArr = new Array(arr.length);
  for(let i = arr.length - 1; i >= 0; i--){
    let index = count[arr[i]] - 1;
    sortedArr[index] = arr[i];
    count[arr[i]]--;
  }
  arr = [...sortedArr];
}
```
**🔗Source:** https://www.youtube.com/watch?v=OKd534EWcdk

### Q27: How is a radix sort algorithm implemented?
> Difficulty : ⭐⭐⭐⭐

```java
void countingSort(Integer arr[], int place){
        int[] count = new int[100];
        Integer[] sortedArr = new Integer[arr.length];
        Arrays.fill(count,0);
        int i;

        for(i = 0; i < arr.length; i++){
            count[ (arr[i]/place)%10 ]++;
        }

        for( i = 1; i < 100; i++){
            count[i] += count[i - 1];
        }


        for(i = arr.length - 1; i >= 0; i--){
           sortedArr[count[(arr[i]/place)%10 ] - 1] = arr[i];
           count[(arr[i]/place)%10 ]--;
        }

        for(i = 0; i < arr.length; i++){
            arr[i] = sortedArr[i];
        }

    }

Integer[] radixSort(Integer arr[]){
    int max = Collections.max(Arrays.asList(arr));
    for(int place = 1; max / place > 0; place *= 10)
        countingSort(arr,place);

    return arr;
}
```
**🔗Source:** https://www.youtube.com/watch?v=XiuSW_mEn7g&t=22s

### Q28: How do you implement a bucket sort algorithm?
> Difficulty : ⭐⭐⭐

```java
Integer[] bucketSort(Integer[] arr){
        int max = Collections.max(Arrays.asList(arr));
        List<List<Integer>> bucket = new ArrayList<>(10);
        int i;
        for(i = 0; i < 10; i++){
            bucket.add(new ArrayList<>());
        }
        // First: find the divider = ceil((max + 1) / 10)
        int divider = (int)Math.ceil((double)(max + 1) / 10);

        // Next, Loop through arr and add number to bucket at index j = floor(arr[i] / divider)
        for(i = 0; i < arr.length; i++){
            int j = arr[i] / divider;
            bucket.get(j).add(arr[i]);
        }

        // Loop through every bucket and sort its bucket with insertSort
        for(List<Integer> b : bucket){
            insertSort(b);
        }

        // Combine all buckets to sortedArr
        List<Integer> sortedArr = new ArrayList<>();
        for(List<Integer> b : bucket){
            sortedArr.addAll(b);
        }

        return sortedArr.toArray(arr);
    }
```
**🔗Source:** https://www.youtube.com/watch?v=geVyIsFpxUs

Q29: How to calculate square root without using library?
> Difficulty : ⭐⭐⭐⭐⭐

```java
 static double sqrt(double number) {
        double t;

        double squareRoot = number / 2;

        do {
            t = squareRoot;
            squareRoot = (t + (number / t)) / 2;
        } while ((t - squareRoot) != 0);

        return squareRoot;
    }
```
**🔗Source:** https://www.programcreek.com/2012/02/java-calculate-square-root-without-using-library-method/