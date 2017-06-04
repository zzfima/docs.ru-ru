---
title: "Использование асинхронных сокетов сервера | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "протоколы приложений, сокеты"
  - "отправка данных, сокеты"
  - "класс Socket, асинхронные сокеты сервера"
  - "запросы данных, сокеты"
  - "сокеты, асинхронные сокеты сервера"
  - "запрос данных из Интернета, сокеты"
  - "сокеты сервера"
  - "получение данных, сокеты"
  - "асинхронные сокеты сервера"
  - "протоколы, сокеты"
  - "Интернет, сокеты"
ms.assetid: 813489a9-3efd-41b6-a33f-371d55397676
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Использование асинхронных сокетов сервера
Асинхронные сокета сервера используют модель программирования платформы .NET Framework асинхронную для обработки запросов сетевой службы.  Класс <xref:System.Net.Sockets.Socket> соответствует стандартному шаблону именования платформы .NET Framework асинхронным; например, метод <xref:System.Net.Sockets.Socket.Accept%2A> синхронный соответствует <xref:System.Net.Sockets.Socket.BeginAccept%2A> и асинхронным методам <xref:System.Net.Sockets.Socket.EndAccept%2A>.  
  
 Асинхронное сокета сервера требуется, чтобы метод начинает принимать запросы на соединение по сети, обратного вызова обрабатывать запросы соединения и начинается получение данных из сети и обратного вызова для завершения получение данных.  Все эти методы описаны ниже в этом подразделе.  
  
 В следующем примере начать принимать запросы на соединение по сети, метод `StartListening` инициализирует **Сокет**, а затем использует метод **BeginAccept** чтобы начать принимать новые соединения.  Обратный вызов выполнить вызов, когда новый запрос на соединение получен для сокета.  Он отвечает за получение экземпляра **Сокет**, обрабатывающий соединение и обработка то **Сокет** в поток, который будет обрабатывать запрос.  Метод обратного вызова реализует делегат принимать <xref:System.AsyncCallback>; он возвращает значение void и принимает один параметр типа <xref:System.IAsyncResult>.  В следующем примере оболочка обратного вызова.  
  
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
  
 Метод **BeginAccept** принимает 2 параметров **AsyncCallback**, делегат, указывающий на метод обратного вызова принимать и объект, используемый для передачи сведений о состоянии в метод обратного вызова.  В следующем примере **Сокет** прослушивания передается методу обратного вызова с помощью параметра *состояния*.  В этом примере создается делегат **AsyncCallback** и начинает принимать подключения из сети.  
  
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
  
 Сокета, использующих асинхронные потоки из пула потоков системы для обработки входящих подключений.  Один поток отвечает за принятие подключений, другой поток используется для обработки каждое входящее соединение, а другой поток отвечает за получение данных из подключения.  Они могут являться одним и тем же потоке, в зависимости от которого поток присвоить пулом потоков.  В следующем примере класс <xref:System.Threading.ManualResetEvent?displayProperty=fullName> приостанавливает выполнение основного потока и сигналов, когда выполнение может быть продолжен.  
  
 В следующем примере показан асинхронный метод, который создает асинхронное сокета TCP\/IP на локальном компьютере и начинает принимать подключения.  Она предполагает, что глобальная **ManualResetEvent** метод с именем `allDone`, что член класса с именем `SocketListener` и что определяется именованный метод обратного вызова `acceptCallback`.  
  
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
  
 Обратный вызов выполнить \(`acceptCallback` в предыдущем примере\) отвечает за передачи сигналов потока основного приложения, чтобы продолжить обработку, устанавливать соединение с клиентом и запустить асинхронное чтение данных из клиента.  В следующем примере первая часть реализации метода `acceptCallback`.  Этот раздел метода сигнализирует потока основного приложения, чтобы продолжить обработку и устанавливает подключения к клиенту.  Он принимает глобальное **ManualResetEvent** с именем `allDone`.  
  
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
  
 Чтение данных из сокета клиента требуется объект состояния, который передает значения между асинхронными вызовами.  Следующий пример реализует объект состояния для получения строки из удаленного клиента.  Он содержит поля для сокета клиента буфера данных для получения данных и <xref:System.Text.StringBuilder> для создания строки данных, отправленную клиентом.  Устанавливать эти поля объекта состояния разрешает их значения для сохранения через несколько вызовов для чтения данных из сокета клиента.  
  
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
  
 Раздел метода `acceptCallback`, который запускает получение данных из сокета клиента сначала инициализирует экземпляр класса `StateObject`, а затем вызывает метод <xref:System.Net.Sockets.Socket.BeginReceive%2A> чтобы начать чтение данных из сокета клиента в асинхронном режиме.  
  
 В следующем примере приведен полный метод `acceptCallback`.  Она предполагает, что с именем **ManualResetEvent** глобальное `allDone,`, класс `StateObject` указывают, что метод `readCallback` определенный в классе с именем `SocketListener`.  
  
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
  
 Конечный метод, который требуется реализовывать для асинхронного сервера сокета чтение метод обратного вызова, который получает данные, отправленные клиентом.  В качестве обратного вызова, прочитанный обратный вызов делегата **AsyncCallback**.  Этот метод считывает один или более байтов из сокета клиента в буфер данных и затем вызывает метод **BeginReceive** повторно до тех пор, пока данные, отправленные клиентом.  Как только все сообщение было считано из клиента, строка выводится на консоль и закрыто сокета сервера при обработке подключения к клиенту.  
  
 Следующий пример реализует метод `readCallback`.  Она предполагает, что класс `StateObject` определен.  
  
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
  
## См. также  
 [Использование синхронного сокета сервера](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)   
 [Пример асинхронного сокета сервера](../../../docs/framework/network-programming/asynchronous-server-socket-example.md)   
 [Threading](../../../docs/standard/threading/index.md)   
 [Прослушивание с помощью сокетов](../../../docs/framework/network-programming/listening-with-sockets.md)