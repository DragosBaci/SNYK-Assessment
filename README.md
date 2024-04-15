# SNYK-Assessment

1.Stacks and queues are both abstract data structures that have restrained functionality. A queue works on the FIFO principle, meaning first in first out, while a stack works on the LIFO principle, last in first out. Simply put, in a stack elements are added and removed from the top, while in a queue, elements are added at the back and removed at the front.

2.An array is a data structure that groups a bunch of items in memory one after the other. 
The main advantage of this approach is that you can access any item in constant time because the computer knows how much memory each item takes and it can jump by the offset of the index to the exact location of the item you are trying to access.
The main disadvantage is that you need to specify the size of the array on its creation, meaning that you can also make the mistake of creating a larger or smaller array than it is necessary.
A linked list is a data structure that is made of nodes. A node contains some data and a pointer to the location of the next node. 
The advantages are the fact that your list can grow or shrink as much as you need it to (excluding hardware limitations of course) and compared to an array where the insertion is memory intensive as you approach the start of it because you need to shift all the other items to make room for the new one, in a linked list you can just change the pointers to point to your new item.
The disadvantage is that a linked list is all over the place in memory, you can’t index it unless you traverse it because there is no way to know the location of a node without checking the previous nodes.

3.HTTP and HTTPS are protocols used to communicate between server and client. The difference between them is that HTTPS is a secure version of HTTP where it uses a SSL certificate to validate the identity and then encrypt all the data is sent.

4.Some of the most common HTTP response codes that I have ran into were:
200 – I made a good request
201 – when I create something on the server
400 – when I sent some bad format data from my front-end to back-end
403 – when I forgot to add the token in the headers or it expired
404 – when the resource I requested was not found on the backend
500 – when I forgot to handle an exception on backend so it sends me a generic response

5.Authentication is the process of verifying the identity of a user while authorization is checking if the user has the permission to access the resources he is trying to access or do certain actions on the application.

6.I think the best analogy is a giant library where you can ask the librarian for anything you want. This one is a special librarian because even though he has trillions of books in his library, he always knows where to find what you are looking for, and he will bring you at least a book related to what you are trying to get.

7.The most common approach would be to iterate n times and print each line. This can be done in multiple ways but I will choose the most simple version.
```typescript
function printStaircase(n: number): void {
    for (let i = 1; i <= n; i++) {
        const spaces: string = ' '.repeat(n - i);
        const hashes: string = '# '.repeat(i).trim();
        console.log(spaces + hashes);
    }
}

printStaircase(4);

    8.
 function encryptText(text: string): void {
  const removedSpacesText: string = text.split(' ').join('');

  let squareRootOfText: number = Math.sqrt(removedSpacesText.length);

  const rows: number = Math.floor(squareRootOfText);
  const columns: number = Math.ceil(squareRootOfText);

  let grid: string[] = [];

  for (let i = 0; i < rows; i++) {
    let row: string = '';
    for (let j = 0; j < columns; j++) {
      let index: number = i * columns + j;
      if (index < removedSpacesText.length) {
        row += removedSpacesText[index];
      }
    }
    grid.push(row);
  }
  console.log(grid);
}

encryptText('if man was meant to stay on the ground god would have given us roots');
