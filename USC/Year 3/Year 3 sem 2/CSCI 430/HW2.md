user/src/fhttpd

ls ->webserver.c

Looking for places where there is buffer, and user input to that buffer
Run by ./webserver 8080 (port number)

Sent request by curl localhost:8080 instead of tellnet 

you could do curl localhost:8080/index.html

To send a bigger request its the part after the slash

curl localhost:8080/index.jufjoirjgosirjgosirejgoiejriogoiejgoiejgoerijg

or bigger

Instead, put the input into the file
For a text editor in linux, use nano input.txt
to give it to the server,
- curl localhost:8080/`cat input.txt` 
    - Put the command in the quotes then put the output of the command replaced with that
- To find out how long it is, wc input.txt (has to have without newlines)

### something else
run it in a debugger
gdb ./webserver
sudo apt install gdb

(gdb) ser args 8080
run
 1024
When the gdb crashes, you can find the line number of the code and where to fix it, since there are 3 buffers. 


##### patching code
As you go thru hw2, one of the stack buffer overflow code examples will be in it, and you should just replace it with the safe version online.
strncpy(char dest, char src, n).