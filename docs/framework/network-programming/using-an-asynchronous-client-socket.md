---
title: "Использование асинхронных сокетов клиента | Microsoft Docs"
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
  - "запросы данных, сокеты"
  - "асинхронные сокеты клиента"
  - "класс Socket, асинхронные сокеты клиента"
  - "запрос данных из Интернета, сокеты"
  - "сокеты, асинхронные сокеты клиента"
  - "получение данных, сокеты"
  - "протоколы, сокеты"
  - "Интернет, сокеты"
  - "сокеты клиента"
ms.assetid: fd85bc88-e06c-467d-a30d-9fd7cffcfca1
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Использование асинхронных сокетов клиента
Асинхронное сокет клиента не приостанавливает приложение при ожидании завершения операции сети.  Вместо этого он использует стандартную модель программирования платформы .NET Framework асинхронную для обработки сетевое подключение в одном потоке, пока приложение продолжает свою работу в исходном потоке.  Асинхронные сокета подходят для приложений, выполняющих heavy использование сети или не может ожидать сетевые операции, перед тем как продолжить.  
  
 Класс <xref:System.Net.Sockets.Socket> соответствуют основному шаблону именования платформы .NET Framework для асинхронных методов; например, метод <xref:System.Net.Sockets.Socket.Receive%2A> синхронный соответствует <xref:System.Net.Sockets.Socket.BeginReceive%2A> и асинхронным методам <xref:System.Net.Sockets.Socket.EndReceive%2A>.  
  
 Асинхронные операции требуют обратный вызов получает результат операции.  Если приложению не требуется знать результат, обратный вызов не требуется.  Код примера в этом разделе показано использование метода для запуска подключиться к устройству сети и обратного вызова для завершения подключения, метод для запуска отправлять данные, и обратный вызов для завершения отправки, и метод для запуска получение данных и обратный вызов, чтобы завершить получение данных.  
  
 Асинхронные сокета используют несколько потоков из пула потоков системы для обработки сетевые подключения.  Один поток отвечает за инициирование отправки или получения данных. другое потоке общее соединение в устройство сети и отправляет и получает данные.  В следующих примерах экземпляров класса <xref:System.Threading.ManualResetEvent?displayProperty=fullName> используются, чтобы приостановить выполнение основного потока и указать, когда выполнение может быть продолжен.  
  
 В следующем примере подключение асинхронное сокет в устройство в сети, метод `Connect`  инициализирует **Сокет**, а затем вызывает метод [BeginConnect](frlrfsystemnetsocketssocketclassconnecttopic), указав удаленную конечную точку, которая представляет устройство в сети, обратный вызов подключения и объект состояния **Сокет**\(клиента\), который используется для передачи информации о состоянии между асинхронными вызовами.  Пример реализует метод `Connect` для подключения указанный **Сокет** к конкретной конечной точке.  Он принимает глобальное **ManualResetEvent** с именем `connectDone`.  
  
```vb  
Public Shared Sub Connect(remoteEP As EndPoint, client As Socket)  
    client.BeginConnect(remoteEP, _  
       AddressOf ConnectCallback, client)  
  
    connectDone.WaitOne()  
End Sub 'Connect  
```  
  
```csharp  
public static void Connect(EndPoint remoteEP, Socket client) {  
    client.BeginConnect(remoteEP,   
        new AsyncCallback(ConnectCallback), client );  
  
   connectDone.WaitOne();  
}  
```  
  
 Обратный вызов `ConnectCallback` подключения реализует делегат <xref:System.AsyncCallback>.  Он подключается к удаленному устройство, когда удаленное устройство доступно, а затем сигнализирует поток приложения, что соединение завершено, установив **ManualResetEvent**`connectDone`.  В следующем примере реализован метод `ConnectCallback`.  
  
```vb  
Private Shared Sub ConnectCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete the connection.  
        client.EndConnect(ar)  
  
        Console.WriteLine("Socket connected to {0}", _  
            client.RemoteEndPoint.ToString())  
  
        ' Signal that the connection has been made.  
        connectDone.Set()  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'ConnectCallback  
  
```  
  
```csharp  
private static void ConnectCallback(IAsyncResult ar) {  
    try {  
        // Retrieve the socket from the state object.  
        Socket client = (Socket) ar.AsyncState;  
  
        // Complete the connection.  
        client.EndConnect(ar);  
  
        Console.WriteLine("Socket connected to {0}",  
            client.RemoteEndPoint.ToString());  
  
        // Signal that the connection has been made.  
        connectDone.Set();  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 Метод `Send` примера кодирует данные заданной строки в формате ASCII и отправляет его в асинхронном режиме в устройство сети, представленного указанным гнездом.  В следующем примере реализуется метод `Send`.  
  
```vb  
Private Shared Sub Send(client As Socket, data As [String])  
    ' Convert the string data to byte data using ASCII encoding.  
    Dim byteData As Byte() = Encoding.ASCII.GetBytes(data)  
  
    ' Begin sending the data to the remote device.  
    client.BeginSend(byteData, 0, byteData.Length, SocketFlags.None, _  
        AddressOf SendCallback, client)  
End Sub 'Send  
  
```  
  
```csharp  
private static void Send(Socket client, String data) {  
    // Convert the string data to byte data using ASCII encoding.  
    byte[] byteData = Encoding.ASCII.GetBytes(data);  
  
    // Begin sending the data to the remote device.  
    client.BeginSend(byteData, 0, byteData.Length, SocketFlags.None,  
        new AsyncCallback(SendCallback), client);  
}  
```  
  
 Обратный вызов `SendCallback` отправлять реализует делегат <xref:System.AsyncCallback>.  Он отправляет данные, когда устройство сети готов получить.  В следующем примере показана реализация метода `SendCallback`.  Он принимает глобальное **ManualResetEvent** с именем `sendDone`.  
  
```vb  
Private Shared Sub SendCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete sending the data to the remote device.  
        Dim bytesSent As Integer = client.EndSend(ar)  
        Console.WriteLine("Sent {0} bytes to server.", bytesSent)  
  
        ' Signal that all bytes have been sent.  
        sendDone.Set()  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'SendCallback  
  
```  
  
```csharp  
private static void SendCallback(IAsyncResult ar) {  
    try {  
        // Retrieve the socket from the state object.  
        Socket client = (Socket) ar.AsyncState;  
  
        // Complete sending the data to the remote device.  
        int bytesSent = client.EndSend(ar);  
        Console.WriteLine("Sent {0} bytes to server.", bytesSent);  
  
        // Signal that all bytes have been sent.  
        sendDone.Set();  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 Чтение данных из сокета клиента требуется объект состояния, который передает значения между асинхронными вызовами.  Следующий класс объект состояния примера для получения данных из сокета клиента.  Он содержит поле для сокета клиента буфера для полученных данных и <xref:System.Text.StringBuilder> для хранения строки входящих данных.  Устанавливать эти поля объекта состояния разрешает их значения для сохранения через несколько вызовов для чтения данных из сокета клиента.  
  
```vb  
Public Class StateObject  
    ' Client socket.  
    Public workSocket As Socket = Nothing   
    ' Size of receive buffer.  
    Public BufferSize As Integer = 256  
    ' Receive buffer.  
    Public buffer(256) As Byte   
    ' Received data string.  
    Public sb As New StringBuilder()  
End Class 'StateObject  
  
```  
  
```csharp  
public class StateObject {  
    // Client socket.  
    public Socket workSocket = null;  
    // Size of receive buffer.  
    public const int BufferSize = 256;  
    // Receive buffer.  
    public byte[] buffer = new byte[BufferSize];  
    // Received data string.  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 Метод `Receive` примера настраивает объект состояния, а затем вызывает метод **BeginReceive** для чтения данных из сокета клиента в асинхронном режиме.  В следующем примере реализуется метод `Receive`.  
  
```vb  
Private Shared Sub Receive(client As Socket)  
    Try  
        ' Create the state object.  
        Dim state As New StateObject()  
        state.workSocket = client  
  
        ' Begin receiving the data from the remote device.  
        client.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf ReceiveCallback, state)  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'Receive  
  
```  
  
```csharp  
private static void Receive(Socket client) {  
    try {  
        // Create the state object.  
        StateObject state = new StateObject();  
        state.workSocket = client;  
  
        // Begin receiving the data from the remote device.  
        client.BeginReceive( state.buffer, 0, StateObject.BufferSize, 0,  
            new AsyncCallback(ReceiveCallback), state);  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 Обратный вызов `ReceiveCallback` получение реализует делегат **AsyncCallback**.  Он получает данные из устройства сети и создает строку сообщения.  Он считывает один или несколько сетевых в буфер байты данных из данных, а затем вызывает метод **BeginReceive** повторно до тех пор, пока данные, отправленные клиентом.  Как только все данные считываются от клиента, `ReceiveCallback` сигнализирует поток приложения завершена, что данные путем установки **ManualResetEvent** `sendDone`.  
  
 В следующем примере кода реализуется метод `ReceiveCallback` .  Он принимает глобальную именованную строку, которая содержит `response` полученную строку и глобальное **ManualResetEvent** именованными `receiveDone`.  Сервер должен закрыть сокет клиента правильно для завершения сеанса сети.  
  
```vb  
Private Shared Sub ReceiveCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the state object and the client socket   
        ' from the asynchronous state object.  
        Dim state As StateObject = CType(ar.AsyncState, StateObject)  
        Dim client As Socket = state.workSocket  
  
        ' Read data from the remote device.  
        Dim bytesRead As Integer = client.EndReceive(ar)  
  
        If bytesRead > 0 Then  
            ' There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, _  
                bytesRead))  
  
            '  Get the rest of the data.  
            client.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
                AddressOf ReceiveCallback, state)  
        Else  
            ' All the data has arrived; put it in response.  
            If state.sb.Length > 1 Then  
                response = state.sb.ToString()  
            End If  
            ' Signal that all bytes have been received.  
            receiveDone.Set()  
        End If  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'ReceiveCallback  
  
```  
  
```csharp  
private static void ReceiveCallback( IAsyncResult ar ) {  
    try {  
        // Retrieve the state object and the client socket   
        // from the asynchronous state object.  
        StateObject state = (StateObject) ar.AsyncState;  
        Socket client = state.workSocket;  
        // Read data from the remote device.  
        int bytesRead = client.EndReceive(ar);  
        if (bytesRead > 0) {  
            // There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,bytesRead));  
                //  Get the rest of the data.  
            client.BeginReceive(state.buffer,0,StateObject.BufferSize,0,  
                new AsyncCallback(ReceiveCallback), state);  
        } else {  
            // All the data has arrived; put it in response.  
            if (state.sb.Length > 1) {  
                response = state.sb.ToString();  
            }  
            // Signal that all bytes have been received.  
            receiveDone.Set();  
        }  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
## См. также  
 [Использование синхронного сокета клиента](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)   
 [Прослушивание с помощью сокетов](../../../docs/framework/network-programming/listening-with-sockets.md)   
 [Примеры асинхронных сокетов клиента](../../../docs/framework/network-programming/asynchronous-client-socket-example.md)