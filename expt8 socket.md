There will be 2 files

1. MyServer.java

import java.io.*;

import java.net.*;

public class MyServer

{
public static void main(String[] args)
{
try {
ServerSocket ss=new ServerSocket(6666);
Socket s=ss.accept();//establishes connection
DataInputStream dis=new DataInputStream(s.getInputStream());
String str=(String)dis.readUTF();
System.out.println("message= "+str);
ss.close();
}
catch(Exception e){System.out.println(e);}
}
}

2. MyClient.java

import java.io.*;
import java.net.*;
public class MyClient
{
public static void main(String[] args)
{
try {
Socket s=new Socket("localhost",6666);
DataOutputStream dout=new DataOutputStream(s.getOutputStream());
dout.writeUTF("Hello Server");

dout.flush();
dout.close();
s.close();
}
catch(Exception e){System.out.println(e);}
}
}

Run the programs simultaneously in 2 terminals

<img width="684" alt="image" src="https://user-images.githubusercontent.com/97346786/199730203-c799fdf8-dd74-4ed5-a440-3f8e03419148.png">
