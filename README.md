# Daily Tech Journal

## Testing Software
#### The importance of testing (31.jan.2020)
If a business application doesn't work correctly, the manufacturers can lose the business image, time, money, for some case life as well.

The software test is very important in the reasons above, but for the faster development, a company can overlook building software without the test.

The purposes of the test are checking software working well, but also the satisfaction of the software specifications.

The test can be done by a unit or an integration test. The unit test helps us to write smaller and full-fill single-responsibility code condition. Another advantages of unit test are catching the problems early, more straightforward integration, and improving the architecture.

## General Programming
#### Class method, aka. static method (30.jan.2020)
- c++
```
Class Robot {
  static void hi(name) {
    cout << name << ' hi!!';
  }
}
```
- ruby
```
Class Robot
  def self.hi(name)
    print `${name} hi!!`
  end
end
```

The Class method used to be called as a static method. When the class loads, this static method prepared in memory. The Static method or static variables can be accessed everywhere in application like class.

- class method
```
human_name = 'suhy'
Robot.hi(human_name)
>> suhy hi!!
```
- instance method
```
my_dog = Dog('warr')
my_dog.bark()
>> Woof Woof
```

#### The differences between Session and Cookie (29.jan.2020)
It is different from the data saving place of user's information.
Cookie does not use server's resources, Session uses server's resources.
The session has better at security, and Cookie has better response speed.

## React
#### Why Hooks are preferred than using classes (28.jan.2020)
Hooks provide intuitive API such as useState, useEffect. Using Hooks, we can abstract state-related logic, and it enables us to reuse and share that logic.

## Data structures

```
Data structures (non-primitive)
│
├─ Linear data structures
│  ├─ Array
│  ├─ Linked list
│  ├─ Stack
│  └─ Queue
│
└─ Non linear data structures
   │
   ├─ Graphs
   ├─ Trees
   ├─ Trie
   └─ HashTable
      │
      ├─ Set
      └─ Map
```

#### The differences between Set and Map (27.jan.2020)
Set or Map can be stored in computer memory with an order or as a Hashmap Table.
The case of storing with order is useful to have sorted order, but we could have constant time efficiency using Hashmap Table. So the purpose of using it should be considered, and it needs trade-off for the circumstance.

Set is a mathematical terminology to use in computer programming; it indicates whether an element contained in a Set or not.
And Map is used to store key-value pairs, and this can solve Graph algorithm, frequency algorithm.

#### The differences between Stack and Queue (16.jan.2020)

Queue uses First Input First Output (FIFO). For instance, the people wait for a queue to hop on the bus, the first person in the line will get on the bus.

Stack uses Last Input First Output (LIFO). For example, when I put one piece of paper on the stack of papers, some others will pick first that paper what I put from the pile.

#### The differences between Array and Linked list (14.jan.2020)

The Array is a consistent set of a fixed number of data items. And the Linked list is an ordered set comprising a variable number of data items.

The indexes directly or randomly access the Array. But the Linked list is sequentially accessed, traverse starting from the first node in the list by the pointer.

The Array relatively slow at insertion or deletion as shifting is required, but the Linked list is effective, fast and efficient for that.

However, access time in memory of Linked list is slower. Because, While Array elements physically assigned consecutively in the hardware memory during compile time, Linked list elements are stored randomly in hardware during the run time.

The linear search can search them both. But Array can be searched by binary search, while Linked list is not.

## Ruby
### Closures (24.jan.2020)
Closures often pass into a function as a parameter, a particular part in the function can call the closure.
Closures have Blocks, Procs and Lambda's.

#### Blocks
```sh
class Array
  def some_func
    self.each do |n|
      ...
      x = yield(n)    (n = 3 => 3 ** 2 => 9)
      ...
    end
  end
end

array = [1,2,3,4,5]
array2 = [11,14,20,24,25]
array.some_func do | n |
    n ** 2
end
array2.some_func do | n |
    n ** 2
end
```

The Block is a snipped code, after passing into a function, it can be executed with the 'yield' in the function.
If we want to use the same Block to another array2 or array3, to prevent repeating it, we could use Procs or Lambda's.

#### Procs
```sh
class Array
  def some_func(s)
    self.each do |n|
      ...
      x = s.call(n)    (n = 3 => 3 ** 2 => 9)
      ...
    end
  end
end

array = [1,2,3,4,5]
array2 = [11,14,20,24,25]
square = Proc.new do | n |
    n ** 2
end
array.some_func(square)
array2.some_func(square)
```

#### Lambda's
```
class Array
  def some_func(s)
    self.each do |n|
      ...
      x = s.call(n)    (n = 3 => 3 ** 2 => 9)
      ...
    end
  end
end

array = [1,2,3,4,5]
a = lambda do |n|
  n ** 2
end
array.some_func(a)
```

Uses of Lambda looks similar to Proc.
The difference is that, while Proc doesn't check parameter count, lambda checks parameter count.
```
def some_func(b)
  b.call(1, 2)
end
some_func(Proc.new{ |a, b, c| print a, b, c }) => c == null
some_func(lambda{ |a, b, c| print a, b, c }) => wrong number of parameters error
```

For another difference,
```
def first
  Proc.new { return 'a' }.call
  return 'b'
end

def second
  lambda { return 'a' }.call
  return 'b'
end

print first #=> 'a'
print second #=> 'b'
```
Proc works like code snippet, and once it has seen the return statement, it returns directly.
But lambda works like a keyword, and it will read the function until the end of the line.

## Ruby on Rails
### The advantages of using Ruby on Rails (23.jan.2020)
#### Faster development time
Ruby on Rails minimizes the website development time by 25-50% as compared to other popular web frameworks.

It has many ready-made plugins which are gems, MVC structure, modular design, object-oriented, and huge open-source communities.

### Additional advantages of using Ruby (23.jan.2020)
#### Clean and Simple Syntax
The syntax is modest and compact, which empowers developers to solve complex problems with fewer lines of code. It supports the human-readable code as well.

#### Metaprogramming
Ruby can be designed to read or transform other programs, and even modify itself while running.

## Javascript

### Asynchronous
The response time after sending a request to the server could be slower than code execution time. So we need to use the asynchronous function.

#### Async-await (22.jan.2020)
Async function is written like just general function, but it works like promise function.

An Async function can involve Await; it pauses Async function and waits for promise work; it resumes Async function and returns a result. While the Async function breaks, the calling function runs continuously.

Await keyword only works in an Async function. If we use this out of Async function, it will get a syntax error.

## Rails

### WebSockets

#### ActionCable (21.jan.2020)
Web applications are giving service using the HTTP protocol, half-duplex communication between server and client. For example, chatting app needs to send info from server to client, it uses polling in background service. But, rails 5.0 ActionCable integrates WebSockets to enable bidirectional simultaneous communication between server and client.

### An introduction about Rails 6 framework

This writing is to introduce Rails framework which is a server-side web app framework to a person new to and inexperienced in Rails.

```
source /
│
├─ app /
│  ├─ controllers
│  ├─ models
│  └─ views
│
├─ config /
│  └─ routes
│
└─ db /
   └─ migrate
```

#### MVC (13.jan.2020)

Rails has a model-view-controller (MVC) design pattern. It presents default structures for a database, a web service, and web pages. I am going to talk about this today.

The model contains data for application and often linked to a database. And it has an order which can be used for business purpose. And it does not know user interface; it means it can be reused.

The view generates the user interface, which presents data to the users. Many views can access the same model for different reasons. Once the view created, the data is displayed to the users.

The controller receives events from the outside world, usually through views. It interacts with the model and displays the appropriate view to the users.

#### Routes (14.jan.2020)

```
source /
│
├─ app /
│  └─ controllers /
│     └─ users_controller.rb
│
└─ config /
   └─ routes.rb

[ users_controller.rb ]
  def index
    @users = User.all
  end

[ routes.rb ]
  get 'users#index', as: :users
```

The Router in rails navigates the URL or path to proper controllers. For example, the Router 'users URL' called by external links such as user input or command line, then it will connect to 'users_controller' 'index' method.


## Asymptotic notation

#### *Θ*, *O*, *Ω*, *o*, *ω* notations (20.jan.2020)
For the small size algorithm, the task ends very fast regardless of the effectiveness.
But when the input size is big enough, the efficiency becomes an issue.
So, to calculate the execution time of an algorithm, always we analyze the time for big sized input case, aka Asymptotic notation.

First, Look the three notations.
**Big *Θ*** (theta) notation means an **asymptotic increasing rate** of an algorithm. *Θ*(*f*(*n*)) is a group of matching asymptotic increasing rate with *f*(*n*). For example,
```sh
5n² + 4n + 6 = Θ(n²)
```

**Big *O*** notation means asymptotic **upper bound** of increasing rate, and it calculates **worst case**.
And **Big *Ω*** (omega) notation means an asymptotic **lower bound** of increasing rate, and it calculates the **best case**.

And look deep into the strict definition.
It also has **Little *o*** and **Little *ω***.
**Little *o*** means asymptotic **strict upper bound** of increasing rate.
```sh
5n = O(n)
5n = o(n²)
```
**Little *ω*** means asymptotic **strict lower bound** of increasing rate.
```sh
5n = ω(n)
```

## Software design pattern

Object-oriented languages are manageable to implementing software design patterns. Patterns help improve developer communication. But like always, uses of patterns should not be overloaded more than practical reason.

#### Singleton Pattern (17.jan.2020)

We use this if we want to limit the creation of the class into one object only.
ex) User Interface, Game Board

But it should be used in a limited way. This pattern doesn't fit with a multi-thread system while it can generate only one instance. Also, it could be violating the single responsibility rule. As a conclusion, this pattern needs carefully used.

#### Factory Pattern (17.jan.2020)

When we create a object, this pattern secures producing the same instances.

#### Abstract Factory Pattern (17.jan.2020)

The customer application can access to use of factory with no knowledge of conception through an interface of factories.

## Computer Networking

### Network Layers

Two computers communicate help of network connection. But, if this two has different OS or architecture or even different capacity of data acceptance speed,
how they can communicate with each other in real-time.

#### Five-layer internet protocol stack (15.jan.2020)

```
Protocol stack
│
├─ Application
├─ Transport
├─ Network
├─ Link
└─ Physical
```

Each layers is a package of protocols.

The Application layer includes some protocols, such as the HTTP, SMTP, FTP protocol. It also does transmitting human-readable url domain to the actual address.
Application layer data transported by TCP, UDP protocols in the Transport layer.

Network layer moves Datagram packets from one host to another.
The Network layer combines Transport layer segment and a destination address, like a postal service a letter with a destination address.

The Network layer passes the Datagram down to the Link layer, and the Link layer passes the Datagram up to the Network layer.

Finally, the job of the Physical layer is to move the individual bits within the frame from one node to the next.

But we should mention that it has not only protocol stack around. The network can be organized around seven layers which is OSI (Open System Interconnection) model.

#### 7 layers of OSI model (15.jan.2020)

```
OSI model
│
├─ Application
├─ Presentation
├─ Session
├─ Transport
├─ Network
├─ Data link
└─ Physical
```

OSI(Open System Interconnection) model has 7 layers.

Application layer includes HTTP, FTP, SMTP, ... protocols. That provides services of network applications such as Chrome, Firefox, Outlook, Skype, etc.

Presentation layer receives data from the Application layer. This data is the form of characters and numbers and translated to
machine understandable binary format. And Presentation layer compresses this data for faster sending, also does encryption or decryption.

Session layer helps session management, authentication, authorization.

The Transport layer is envolved segmentation, flow control for speed differences, error control, connection-oriented and connection-less transmission.

The Transport layer provides various forms of process-to-process communication by relying on the network layer's host-to-host communication service.

The function of the Network layer is logical addressing of IPv4 and IPv6, path determination and Routing. When the data arrives, the Routing does finding where to move data with the separation of host and computer address.

Their has two types of addressing, logical addressing is from the Network layer, and physical addressing is from Data link layer.
The Data link layer is embedded as software in the network interface card of the computer.

Physical layer considered by the data communication through optic, electrical transmitting information.

### TCP

#### Three-Way Handshake (14.jan.2020)

We supposed to try a network connection such as opening google.com, what is going to have happened?

1. A client sends to server SYN packet which contains sequence numbers that support the server can connect client; this step is like "Hey, do you want to talk?"
2. The server sends back to the client SYN/ACK packet with the help of sequence numbers; this step is like "Yeah, I received your message, do you want to talk?"
3. Then the client sends ACK packet to the server, like "Yes, let's talk."

=> After this three-way Handshake occurs, the connection is established between the server and the client. Now the packets between them can be transmitted. The protocols loading over TCP is HTTP, FTP, SMTP and SSH.

As it has an opening connection, it also has a closing connection.

1. The client sends the server SYN/ACK packet; "There is no need connection, wants to leave."
2. The server sends back to the client ACK packet, "Yes, I know that you want to leave, then bye."
3. The client sends back to the server ACK packet, "Yes, bye!"
