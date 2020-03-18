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
ms.openlocfilehash: 467804e685d800643c421ed1aad040a842b42886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180632"
---
# <a name="using-an-asynchronous-server-socket"></a>Использование асинхронных сокетов сервера
Асинхронные сокеты сервера используют асинхронную модель программирования платформы .NET Framework для обработки запросов сетевых служб. Класс <xref:System.Net.Sockets.Socket> соответствует стандартному шаблону асинхронного именования платформы .NET Framework. Например, синхронный метод <xref:System.Net.Sockets.Socket.Accept%2A> соответствует асинхронным методам <xref:System.Net.Sockets.Socket.BeginAccept%2A> и <xref:System.Net.Sockets.Socket.EndAccept%2A>.  
  
 Для асинхронного сокета сервера нужен метод, который начинает принимать запросы на соединение из сети, метод обратного вызова, чтобы обрабатывать запросы на соединение и начинать принимать данные, и метод обратного вызова для завершения получения данных. Все эти методы описаны ниже в этом разделе.  
  
 В следующем примере, чтобы начать принимать запросы на соединение по сети, метод `StartListening` инициализирует **сокет**, а затем использует метод **BeginAccept**, чтобы начать принимать новые соединения. Метод обратного вызова приема выполняется, когда сокет получает новый запрос на соединение. Он отвечает за получение экземпляра **сокета**, обрабатывающего соединение, и передачу этого **сокета** в поток, который будет обрабатывать запрос. Метод обратного вызова приема реализует делегат <xref:System.AsyncCallback>; он возвращает значение void и принимает один параметр типа <xref:System.IAsyncResult>. В приведенном ниже примере показана оболочка метода обратного вызова приема.  
  
```vb  
Sub AcceptCallback(ar As IAsyncResult)  
    ' Add the callback code here.  
End Sub 'AcceptCallback  
```  
  
```csharp  
void AcceptCallback(IAsyncResult ar)
{  
    // Add the callback code here.  
}  
```  
  
 Метод **BeginAccept** принимает 2 параметра: делегат **AsyncCallback**, указывающий на метод обратного вызова приема, и объект, используемый для передачи сведений о состоянии в метод обратного вызова. В приведенном ниже примере прослушивающий **сокет** передается в метод обратного вызова с помощью параметра *состояния*. В этом примере создается делегат **AsyncCallback** и начинается прием подключений из сети.  
  
```vb  
listener.BeginAccept( _  
    New AsyncCallback(SocketListener.AcceptCallback),_  
    listener)  
```  
  
```csharp  
listener.BeginAccept(new AsyncCallback(SocketListener.AcceptCallback), listener);  
```  
  
 Асинхронные сокеты используют потоки из системного пула потоков для обработки входящих подключений. Один поток отвечает за принятие подключений, другой — за обработку каждого входящего соединения, а еще один — за получение данных по соединению. Это может быть один и тот же поток, если пул потоков назначил его для выполнения всех трех задач. В приведенном ниже примере класс <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> приостанавливает выполнение главного потока и сообщает, когда оно может быть продолжено.  
  
 В этом примере показан асинхронный метод, который создает на локальном компьютере асинхронный сокет TCP/IP и начинает принимать соединения. В нем предполагается, что существует глобальный экземпляр класса **ManualResetEvent** с именем `allDone`, метод является членом класса `SocketListener` и определен метод обратного вызова с именем `AcceptCallback`.  
  
```vb  
Public Sub StartListening()  
    Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
    Dim localEP = New IPEndPoint(ipHostInfo.AddressList(0), 11000)  
  
    Console.WriteLine($"Local address and port : {localEP.ToString()}")  
  
    Dim listener As New Socket(localEP.Address.AddressFamily, _  
       SocketType.Stream, ProtocolType.Tcp)  
  
    Try  
        listener.Bind(localEP)  
        listener.Listen(10)  
  
        While True  
            allDone.Reset()  
  
            Console.WriteLine("Waiting for a connection...")  
            listener.BeginAccept(New _  
                AsyncCallback(SocketListener.AcceptCallback), _  
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
public void StartListening()
{  
    IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
    IPEndPoint localEP = new IPEndPoint(ipHostInfo.AddressList[0], 11000);  
  
    Console.WriteLine($"Local address and port : {localEP.ToString()}");  
  
    Socket listener = new Socket(localEP.Address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);  
  
    try
    {  
        listener.Bind(localEP);  
        listener.Listen(10);  
  
        while (true)
        {  
            allDone.Reset();  
  
            Console.WriteLine("Waiting for a connection...");  
            listener.BeginAccept(new AsyncCallback(SocketListener.AcceptCallback), listener);  
  
            allDone.WaitOne();  
        }  
    }
    catch (Exception e)
    {  
        Console.WriteLine(e.ToString());  
    }  
  
    Console.WriteLine("Closing the listener...");  
}  
```  
  
 Метод обратного вызова приема (`AcceptCallback` в предыдущем примере) отвечает за передачу сигнала главному потоку приложения о том, что можно продолжать обработку, установление соединения с клиентом и запуск асинхронной операции чтения данных из клиента. Приведенный ниже пример представляет собой первую часть реализации метода `AcceptCallback`. В ней метод сообщает главному потоку приложения о необходимости продолжить обработку и устанавливает соединение с клиентом. Предполагается наличие глобального экземпляра класса **ManualResetEvent** с именем `allDone`.  
  
```vb  
Public Sub AcceptCallback(ar As IAsyncResult)  
    allDone.Set()  
  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Additional code to read data goes here.  
End Sub 'AcceptCallback  
```  
  
```csharp  
public void AcceptCallback(IAsyncResult ar)
{  
    allDone.Set();  
  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Additional code to read data goes here.
}  
```  
  
 Для чтения данных из сокета клиента требуется объект состояния, который передает значения от одного асинхронного вызова к другому. В приведенном ниже примере реализуется объект состояния для получения строки от удаленного клиента. Он содержит поля для сокета клиента, буфер данных для получения данных и <xref:System.Text.StringBuilder> для создания строки данных, отправленной клиентом. Добавление этих полей в объект состояния позволяет сохранять их значения между вызовами для чтения данных из сокета клиента.  
  
```vb  
Public Class StateObject  
    Public workSocket As Socket = Nothing  
    Public BufferSize As Integer = 1024  
    Public buffer(BufferSize) As Byte  
    Public sb As New StringBuilder()  
End Class 'StateObject  
```  
  
```csharp  
public class StateObject
{  
    public Socket workSocket = null;  
    public const int BufferSize = 1024;  
    public byte[] buffer = new byte[BufferSize];  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 Часть метода `AcceptCallback`, которая начинает получать данные из сокета клиента, сначала инициализирует экземпляр класса `StateObject`, а затем вызывает метод <xref:System.Net.Sockets.Socket.BeginReceive%2A>, чтобы начать чтение данных из сокета клиента в асинхронном режиме.  
  
 В приведенном ниже примере показан полный метод `AcceptCallback`. В нем предполагается, что существует глобальный экземпляр класса **ManualResetEvent** с именем `allDone,`, определен класс `StateObject` и определен метод `ReadCallback` в классе с именем `SocketListener`.  
  
```vb  
Public Shared Sub AcceptCallback(ar As IAsyncResult)  
    ' Get the socket that handles the client request.  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Signal the main thread to continue.  
    allDone.Set()  
  
    ' Create the state object.  
    Dim state As New StateObject()  
    state.workSocket = handler  
    handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
        AddressOf AsynchronousSocketListener.ReadCallback, state)  
End Sub 'AcceptCallback  
```  
  
```csharp  
public static void AcceptCallback(IAsyncResult ar)
{  
    // Get the socket that handles the client request.  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Signal the main thread to continue.  
    allDone.Set();  
  
    // Create the state object.  
    StateObject state = new StateObject();  
    state.workSocket = handler;  
    handler.BeginReceive(state.buffer, 0, StateObject.BufferSize, 0,  
        new AsyncCallback(AsynchronousSocketListener.ReadCallback), state);  
}  
```  
  
 Последний метод, который необходимо реализовать для асинхронного сокета сервера, — это метод обратного вызова чтения, который возвращает данные, отправленные клиентом. Как и метод обратного вызова приема, он является делегатом **AsyncCallback**. Этот метод считывает один или несколько байтов из сокета клиента в буфер данных, а затем снова вызывает метод **BeginReceive**, пока данные, отправленные клиентом, не закончатся. После того как сообщение от клиента будет прочитано полностью, строка выводится в консоли, а сокет сервера, обрабатывавший соединение с клиентом, закрывается.  
  
 В приведенном ниже примере реализуется метод `ReadCallback`. В нем предполагается, что определен класс `StateObject`.  
  
```vb  
Public Shared Sub ReadCallback(ar As IAsyncResult)  
    Dim state As StateObject = CType(ar.AsyncState, StateObject)  
    Dim handler As Socket = state.workSocket  
  
    ' Read data from the client socket.
    Dim read As Integer = handler.EndReceive(ar)  
  
    ' Data was read from the client socket.  
    If read > 0 Then  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, read))  
        handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf ReadCallback, state)  
    Else  
        If state.sb.Length > 1 Then  
            ' All the data has been read from the client;  
            ' display it on the console.  
            Dim content As String = state.sb.ToString()  
            Console.WriteLine($"Read {content.Length} bytes from socket. {ControlChars.Cr} Data : {content}")  
        End If  
    End If  
End Sub 'ReadCallback  
```  
  
```csharp  
public static void ReadCallback(IAsyncResult ar)
{  
    StateObject state = (StateObject) ar.AsyncState;  
    Socket handler = state.WorkSocket;  
  
    // Read data from the client socket.  
    int read = handler.EndReceive(ar);  
  
    // Data was read from the client socket.  
    if (read > 0)
    {  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,read));  
        handler.BeginReceive(state.buffer, 0, StateObject.BufferSize, 0,  
            new AsyncCallback(ReadCallback), state);  
    }
    else
    {  
        if (state.sb.Length > 1)
        {  
            // All the data has been read from the client;  
            // display it on the console.  
            string content = state.sb.ToString();  
            Console.WriteLine($"Read {content.Length} bytes from socket.\n Data : {content}");
        }  
        handler.Close();  
    }  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- [Использование синхронного сокета сервера](using-a-synchronous-server-socket.md)
- [Пример асинхронного сокета сервера](asynchronous-server-socket-example.md)
- [Работа с потоками](../../standard/threading/index.md)
- [Прослушивание с помощью сокетов](listening-with-sockets.md)
