---
title: Использование асинхронных сокетов сервера
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- Socket class, asynchronous server sockets
- data requests, sockets
- sockets, asynchronous server sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- asynchronous server sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 813489a9-3efd-41b6-a33f-371d55397676
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f89bf9e3ea9f2b3c385d267cfc77a05ee8eb82d6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2018
ms.locfileid: "47436106"
---
# <a name="using-an-asynchronous-server-socket"></a><span data-ttu-id="7d1b4-102">Использование асинхронных сокетов сервера</span><span class="sxs-lookup"><span data-stu-id="7d1b4-102">Using an Asynchronous Server Socket</span></span>
<span data-ttu-id="7d1b4-103">Асинхронные сокеты сервера используют асинхронную модель программирования платформы .NET Framework для обработки запросов сетевых служб.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-103">Asynchronous server sockets use the .NET Framework asynchronous programming model to process network service requests.</span></span> <span data-ttu-id="7d1b4-104">Класс <xref:System.Net.Sockets.Socket> соответствует стандартному шаблону асинхронного именования платформы .NET Framework. Например, синхронный метод <xref:System.Net.Sockets.Socket.Accept%2A> соответствует асинхронным методам <xref:System.Net.Sockets.Socket.BeginAccept%2A> и <xref:System.Net.Sockets.Socket.EndAccept%2A>.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-104">The <xref:System.Net.Sockets.Socket> class follows the standard .NET Framework asynchronous naming pattern; for example, the synchronous <xref:System.Net.Sockets.Socket.Accept%2A> method corresponds to the asynchronous <xref:System.Net.Sockets.Socket.BeginAccept%2A> and <xref:System.Net.Sockets.Socket.EndAccept%2A> methods.</span></span>  
  
 <span data-ttu-id="7d1b4-105">Для асинхронного сокета сервера нужен метод, который начинает принимать запросы на соединение из сети, метод обратного вызова, чтобы обрабатывать запросы на соединение и начинать принимать данные, и метод обратного вызова для завершения получения данных.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-105">An asynchronous server socket requires a method to begin accepting connection requests from the network, a callback method to handle the connection requests and begin receiving data from the network, and a callback method to end receiving the data.</span></span> <span data-ttu-id="7d1b4-106">Все эти методы описаны ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-106">All these methods are discussed further in this section.</span></span>  
  
 <span data-ttu-id="7d1b4-107">В следующем примере, чтобы начать принимать запросы на соединение по сети, метод `StartListening` инициализирует **сокет**, а затем использует метод **BeginAccept**, чтобы начать принимать новые соединения.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-107">In the following example, to begin accepting connection requests from the network, the method `StartListening` initializes the **Socket** and then uses the **BeginAccept** method to start accepting new connections.</span></span> <span data-ttu-id="7d1b4-108">Метод обратного вызова приема выполняется, когда сокет получает новый запрос на соединение.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-108">The accept callback method is called when a new connection request is received on the socket.</span></span> <span data-ttu-id="7d1b4-109">Он отвечает за получение экземпляра **сокета**, обрабатывающего соединение, и передачу этого **сокета** в поток, который будет обрабатывать запрос.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-109">It is responsible for getting the **Socket** instance that will handle the connection and handing that **Socket** off to the thread that will process the request.</span></span> <span data-ttu-id="7d1b4-110">Метод обратного вызова приема реализует делегат <xref:System.AsyncCallback>; он возвращает значение void и принимает один параметр типа <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-110">The accept callback method implements the <xref:System.AsyncCallback> delegate; it returns a void and takes a single parameter of type <xref:System.IAsyncResult>.</span></span> <span data-ttu-id="7d1b4-111">В приведенном ниже примере показана оболочка метода обратного вызова приема.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-111">The following example is the shell of an accept callback method.</span></span>  
  
```vb  
Sub acceptCallback(ar As IAsyncResult)  
    ' Add the callback code here.  
End Sub 'acceptCallback  
```  
  
```csharp  
void acceptCallback( IAsyncResult ar) {  
    // Add the callback code here.  
}  
```  
  
 <span data-ttu-id="7d1b4-112">Метод **BeginAccept** принимает 2 параметра: делегат **AsyncCallback**, указывающий на метод обратного вызова приема, и объект, используемый для передачи сведений о состоянии в метод обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-112">The **BeginAccept** method takes two parameters, an **AsyncCallback** delegate that points to the accept callback method and an object that is used to pass state information to the callback method.</span></span> <span data-ttu-id="7d1b4-113">В приведенном ниже примере прослушивающий **сокет** передается в метод обратного вызова с помощью параметра *состояния*.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-113">In the following example, the listening **Socket** is passed to the callback method through the *state* parameter.</span></span> <span data-ttu-id="7d1b4-114">В этом примере создается делегат **AsyncCallback** и начинается прием подключений из сети.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-114">This example creates an **AsyncCallback** delegate and starts accepting connections from the network.</span></span>  
  
```vb  
listener.BeginAccept( _  
    New AsyncCallback(SocketListener.acceptCallback),_  
    listener)  
```  
  
```csharp  
listener.BeginAccept(  
    new AsyncCallback(SocketListener.acceptCallback),   
    listener);  
```  
  
 <span data-ttu-id="7d1b4-115">Асинхронные сокеты используют потоки из системного пула потоков для обработки входящих подключений.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-115">Asynchronous sockets use threads from the system thread pool to process incoming connections.</span></span> <span data-ttu-id="7d1b4-116">Один поток отвечает за принятие подключений, другой — за обработку каждого входящего соединения, а еще один — за получение данных по соединению.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-116">One thread is responsible for accepting connections, another thread is used to handle each incoming connection, and another thread is responsible for receiving data from the connection.</span></span> <span data-ttu-id="7d1b4-117">Это может быть один и тот же поток, если пул потоков назначил его для выполнения всех трех задач.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-117">These could be the same thread, depending on which thread is assigned by the thread pool.</span></span> <span data-ttu-id="7d1b4-118">В приведенном ниже примере класс <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> приостанавливает выполнение главного потока и сообщает, когда оно может быть продолжено.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-118">In the following example, the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class suspends execution of the main thread and signals when execution can continue.</span></span>  
  
 <span data-ttu-id="7d1b4-119">В этом примере показан асинхронный метод, который создает на локальном компьютере асинхронный сокет TCP/IP и начинает принимать соединения.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-119">The following example shows an asynchronous method that creates an asynchronous TCP/IP socket on the local computer and begins accepting connections.</span></span> <span data-ttu-id="7d1b4-120">В нем предполагается, что существует глобальный экземпляр класса **ManualResetEvent** с именем `allDone`, метод является членом класса `SocketListener` и определен метод обратного вызова с именем `acceptCallback`.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-120">It assumes that there is a global **ManualResetEvent** named `allDone`, that the method is a member of a class named `SocketListener`, and that a callback method named `acceptCallback` is defined.</span></span>  
  
```vb  
Public Sub StartListening()  
    Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
    Dim localEP = New IPEndPoint(ipHostInfo.AddressList(0), 11000)  
  
    Console.WriteLine("Local address and port : {0}", localEP.ToString())  
  
    Dim listener As New Socket(localEP.Address.AddressFamily, _  
       SocketType.Stream, ProtocolType.Tcp)  
  
    Try  
        listener.Bind(localEP)  
        listener.Listen(10)  
  
        While True  
            allDone.Reset()  
  
            Console.WriteLine("Waiting for a connection...")  
            listener.BeginAccept(New _  
                AsyncCallback(SocketListener.acceptCallback), _  
                listener)  
  
            allDone.WaitOne()  
        End While  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
    Console.WriteLine("Closing the listener...")  
End Sub 'StartListening  
```  
  
```csharp  
public void StartListening() {  
    IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
    IPEndPoint localEP = new IPEndPoint(ipHostInfo.AddressList[0],11000);  
  
    Console.WriteLine("Local address and port : {0}",localEP.ToString());  
  
    Socket listener = new Socket( localEP.Address.AddressFamily,  
        SocketType.Stream, ProtocolType.Tcp );  
  
    try {  
        listener.Bind(localEP);  
        listener.Listen(10);  
  
        while (true) {  
            allDone.Reset();  
  
            Console.WriteLine("Waiting for a connection...");  
            listener.BeginAccept(  
                new AsyncCallback(SocketListener.acceptCallback),   
                listener );  
  
            allDone.WaitOne();  
        }  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
  
    Console.WriteLine( "Closing the listener...");  
}  
```  
  
 <span data-ttu-id="7d1b4-121">Метод обратного вызова приема (`acceptCallback` в предыдущем примере) отвечает за передачу сигнала главному потоку приложения о том, что можно продолжать обработку, установление соединения с клиентом и запуск асинхронной операции чтения данных из клиента.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-121">The accept callback method (`acceptCallback` in the preceding example) is responsible for signaling the main application thread to continue processing, establishing the connection with the client, and starting the asynchronous read of data from the client.</span></span> <span data-ttu-id="7d1b4-122">Приведенный ниже пример представляет собой первую часть реализации метода `acceptCallback`.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-122">The following example is the first part of an implementation of the `acceptCallback` method.</span></span> <span data-ttu-id="7d1b4-123">В ней метод сообщает главному потоку приложения о необходимости продолжить обработку и устанавливает соединение с клиентом.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-123">This section of the method signals the main application thread to continue processing and establishes the connection to the client.</span></span> <span data-ttu-id="7d1b4-124">Предполагается наличие глобального экземпляра класса **ManualResetEvent** с именем `allDone`.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-124">It assumes a global **ManualResetEvent** named `allDone`.</span></span>  
  
```vb  
Public Sub acceptCallback(ar As IAsyncResult)  
    allDone.Set()  
  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Additional code to read data goes here.  
End Sub 'acceptCallback  
```  
  
```csharp  
public void acceptCallback(IAsyncResult ar) {  
    allDone.Set();  
  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Additional code to read data goes here.    
}  
```  
  
 <span data-ttu-id="7d1b4-125">Для чтения данных из сокета клиента требуется объект состояния, который передает значения от одного асинхронного вызова к другому.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-125">Reading data from a client socket requires a state object that passes values between asynchronous calls.</span></span> <span data-ttu-id="7d1b4-126">В приведенном ниже примере реализуется объект состояния для получения строки от удаленного клиента.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-126">The following example implements a state object for receiving a string from the remote client.</span></span> <span data-ttu-id="7d1b4-127">Он содержит поля для сокета клиента, буфер данных для получения данных и <xref:System.Text.StringBuilder> для создания строки данных, отправленной клиентом.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-127">It contains fields for the client socket, a data buffer for receiving data, and a <xref:System.Text.StringBuilder> for creating the data string sent by the client.</span></span> <span data-ttu-id="7d1b4-128">Добавление этих полей в объект состояния позволяет сохранять их значения между вызовами для чтения данных из сокета клиента.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-128">Placing these fields in the state object allows their values to be preserved across multiple calls to read data from the client socket.</span></span>  
  
```vb  
Public Class StateObject  
    Public workSocket As Socket = Nothing  
    Public BufferSize As Integer = 1024  
    Public buffer(BufferSize) As Byte  
    Public sb As New StringBuilder()  
End Class 'StateObject  
```  
  
```csharp  
public class StateObject {  
    public Socket workSocket = null;  
    public const int BufferSize = 1024;  
    public byte[] buffer = new byte[BufferSize];  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 <span data-ttu-id="7d1b4-129">Часть метода `acceptCallback`, которая начинает получать данные из сокета клиента, сначала инициализирует экземпляр класса `StateObject`, а затем вызывает метод <xref:System.Net.Sockets.Socket.BeginReceive%2A>, чтобы начать чтение данных из сокета клиента в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-129">The section of the `acceptCallback` method that starts receiving the data from the client socket first initializes an instance of the `StateObject` class and then calls the <xref:System.Net.Sockets.Socket.BeginReceive%2A> method to start reading the data from the client socket asynchronously.</span></span>  
  
 <span data-ttu-id="7d1b4-130">В приведенном ниже примере показан полный метод `acceptCallback`.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-130">The following example shows the complete `acceptCallback` method.</span></span> <span data-ttu-id="7d1b4-131">В нем предполагается, что существует глобальный экземпляр класса **ManualResetEvent** с именем `allDone,`, определен класс `StateObject` и определен метод `readCallback` в классе с именем `SocketListener`.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-131">It assumes that there is a global **ManualResetEvent** named `allDone,` that the `StateObject` class is defined, and that the `readCallback` method is defined in a class named `SocketListener`.</span></span>  
  
```vb  
Public Shared Sub acceptCallback(ar As IAsyncResult)  
    ' Get the socket that handles the client request.  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Signal the main thread to continue.  
    allDone.Set()  
  
    ' Create the state object.  
    Dim state As New StateObject()  
    state.workSocket = handler  
    handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
        AddressOf AsynchronousSocketListener.readCallback, state)  
End Sub 'acceptCallback  
```  
  
```csharp  
public static void acceptCallback(IAsyncResult ar) {  
    // Get the socket that handles the client request.  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Signal the main thread to continue.  
    allDone.Set();  
  
    // Create the state object.  
    StateObject state = new StateObject();  
    state.workSocket = handler;  
    handler.BeginReceive( state.buffer, 0, StateObject.BufferSize, 0,  
        new AsyncCallback(AsynchronousSocketListener.readCallback), state);  
}  
```  
  
 <span data-ttu-id="7d1b4-132">Последний метод, который необходимо реализовать для асинхронного сокета сервера, — это метод обратного вызова чтения, который возвращает данные, отправленные клиентом.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-132">The final method that needs to be implemented for the asynchronous socket server is the read callback method that returns the data sent by the client.</span></span> <span data-ttu-id="7d1b4-133">Как и метод обратного вызова приема, он является делегатом **AsyncCallback**.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-133">Like the accept callback method, the read callback method is an **AsyncCallback** delegate.</span></span> <span data-ttu-id="7d1b4-134">Этот метод считывает один или несколько байтов из сокета клиента в буфер данных, а затем снова вызывает метод **BeginReceive**, пока данные, отправленные клиентом, не закончатся.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-134">This method reads one or more bytes from the client socket into the data buffer and then calls the **BeginReceive** method again until the data sent by the client is complete.</span></span> <span data-ttu-id="7d1b4-135">После того как сообщение от клиента будет прочитано полностью, строка выводится в консоли, а сокет сервера, обрабатывавший соединение с клиентом, закрывается.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-135">Once the entire message has been read from the client, the string is displayed on the console and the server socket handling the connection to the client is closed.</span></span>  
  
 <span data-ttu-id="7d1b4-136">В приведенном ниже примере реализуется метод `readCallback`.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-136">The following sample implements the `readCallback` method.</span></span> <span data-ttu-id="7d1b4-137">В нем предполагается, что определен класс `StateObject`.</span><span class="sxs-lookup"><span data-stu-id="7d1b4-137">It assumes that the `StateObject` class is defined.</span></span>  
  
```vb  
Public Shared Sub readCallback(ar As IAsyncResult)  
    Dim state As StateObject = CType(ar.AsyncState, StateObject)  
    Dim handler As Socket = state.workSocket  
  
    ' Read data from the client socket.   
    Dim read As Integer = handler.EndReceive(ar)  
  
    ' Data was read from the client socket.  
    If read > 0 Then  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, read))  
        handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf readCallback, state)  
    Else  
        If state.sb.Length > 1 Then  
            ' All the data has been read from the client;  
            ' display it on the console.  
            Dim content As String = state.sb.ToString()  
            Console.WriteLine("Read {0} bytes from socket." + _  
                ControlChars.Cr + " Data : {1}", content.Length, content)  
        End If  
    End If  
End Sub 'readCallback  
```  
  
```csharp  
public static void readCallback(IAsyncResult ar) {  
    StateObject state = (StateObject) ar.AsyncState;  
    Socket handler = state.WorkSocket;  
  
    // Read data from the client socket.  
    int read = handler.EndReceive(ar);  
  
    // Data was read from the client socket.  
    if (read > 0) {  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,read));  
        handler.BeginReceive(state.buffer,0,StateObject.BufferSize, 0,  
            new AsyncCallback(readCallback), state);  
    } else {  
        if (state.sb.Length > 1) {  
            // All the data has been read from the client;  
            // display it on the console.  
            string content = state.sb.ToString();  
            Console.WriteLine("Read {0} bytes from socket.\n Data : {1}",  
               content.Length, content);  
        }  
        handler.Close();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d1b4-138">См. также</span><span class="sxs-lookup"><span data-stu-id="7d1b4-138">See Also</span></span>  
 [<span data-ttu-id="7d1b4-139">Использование синхронного сокета сервера</span><span class="sxs-lookup"><span data-stu-id="7d1b4-139">Using a Synchronous Server Socket</span></span>](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)  
 [<span data-ttu-id="7d1b4-140">Пример асинхронного сокета сервера</span><span class="sxs-lookup"><span data-stu-id="7d1b4-140">Asynchronous Server Socket Example</span></span>](../../../docs/framework/network-programming/asynchronous-server-socket-example.md)  
 [<span data-ttu-id="7d1b4-141">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="7d1b4-141">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="7d1b4-142">Прослушивание с помощью сокетов</span><span class="sxs-lookup"><span data-stu-id="7d1b4-142">Listening with Sockets</span></span>](../../../docs/framework/network-programming/listening-with-sockets.md)
