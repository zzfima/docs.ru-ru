---
title: Использование асинхронных сокетов клиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- asynchronous client sockets
- Socket class, asynchronous client sockets
- requesting data from Internet, sockets
- sockets, asynchronous client sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: fd85bc88-e06c-467d-a30d-9fd7cffcfca1
ms.openlocfilehash: 748745ca6799005dccdbfcbcc37a8c2a38f2a88e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180648"
---
# <a name="using-an-asynchronous-client-socket"></a>Использование асинхронных сокетов клиента
Асинхронный сокет клиента не приостанавливает работу приложения на то время, пока выполняются сетевые операции. Вместо этого он использует стандартную модель асинхронного программирования .NET Framework для обработки операций сетевого подключения в одном потоке, пока приложение продолжает работу в изначальном потоке. Асинхронные сокеты подходят для приложений, которые интенсивно используют сеть или не могут ждать, пока сетевые операции завершатся.  
  
 Класс <xref:System.Net.Sockets.Socket> соответствует шаблону именования платформы .NET Framework для асинхронных методов. Например, синхронный метод <xref:System.Net.Sockets.Socket.Receive%2A> соответствует асинхронным методам <xref:System.Net.Sockets.Socket.BeginReceive%2A> и <xref:System.Net.Sockets.Socket.EndReceive%2A>.  
  
 Чтобы вернуть результат, асинхронным операциям требуется метод обратного вызова. Если приложению не требуется результат, то метод обратного вызова не нужен. В примере кода в этом разделе демонстрируется использование метода для инициации подключения к сетевому устройству и метода обратного вызова для завершения подключения, метода, который начинает отправку данных, и метода обратного вызова, завершающего отправку, а также метода, который начинает получение данных, и метода обратного вызова, завершающего получение.  
  
 Асинхронные сокеты используют несколько потоков из системного пула потоков для обработки сетевых подключений. Один поток отвечает за инициацию отправки или получения данных, а другие завершают подключение к сетевому устройству, а также отправляют или получают данные. В приведенном ниже примере экземпляры класса <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> приостанавливают выполнение главного потока и сообщают, когда оно может быть продолжено.  
  
 В приведенном ниже примере для подключения асинхронного сокета к сетевому устройству метод `Connect` инициализирует объект **Socket**, а затем вызывает метод <xref:System.Net.Sockets.Socket.Connect%2A?displayProperty=nameWithType>, передавая удаленную конечную точку, которая представляет сетевое устройство, метод обратного вызова для подключения и объект состояния (объект **Socket** клиента), который служит для передачи сведений о состоянии между асинхронными вызовами. В этом примере реализуется метод `Connect` для подключения указанного объекта **Socket** к определенной конечной точке. Предполагается наличие глобального экземпляра класса **ManualResetEvent** с именем `connectDone`.  
  
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
  
 Метод обратного вызова подключения `ConnectCallback` реализует делегат <xref:System.AsyncCallback>. Он подключается к удаленному устройству, если оно доступно, а затем сообщает потоку приложения, что подключение завершено, задавая **ManualResetEvent** `connectDone`. В следующем коде реализуется метод `ConnectCallback`:  
  
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
  
 Метод `Send` из примера кодирует предоставленные строковые данные в формате ASCII и отправляет их асинхронно сетевому устройству, представленному указанным сокетом. В следующем примере реализуется метод `Send`:  
  
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
  
 Метод обратного вызова отправки `SendCallback` реализует делегат <xref:System.AsyncCallback>. Он отправляет данные, когда сетевое устройство готово к их приему. В приведенном ниже примере показана реализация метода `SendCallback`. Предполагается наличие глобального экземпляра класса **ManualResetEvent** с именем `sendDone`.  
  
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
  
 Для чтения данных из сокета клиента требуется объект состояния, который передает значения от одного асинхронного вызова к другому. Следующий класс — это пример объекта состояния для получения данных из сокета клиента. Он содержит поле для сокета клиента, буфер для принимаемых данных и объект <xref:System.Text.StringBuilder> для хранения полученной строки данных. Добавление этих полей в объект состояния позволяет сохранять их значения между вызовами для чтения данных из сокета клиента.  
  
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
  
 Метод `Receive` из примера создает объект состояния, а затем вызывает метод **BeginReceive** для чтения данных из сокета клиента в асинхронном режиме. В следующем примере реализуется метод `Receive`:  
  
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
  
 Метод обратного вызова получения `ReceiveCallback` реализует делегат **AsyncCallback**. Он получает данные от сетевого устройства и формирует строку сообщения. Этот метод считывает один или несколько байтов данных из сети в буфер данных, а затем снова вызывает метод **BeginReceive**, пока данные, отправленные клиентом, не закончатся. После считывания всех данных из клиента `ReceiveCallback` сообщает потоку приложения о том, что данные закончились, задавая **ManualResetEvent** `sendDone`.  
  
 В приведенном ниже примере реализуется метод `ReceiveCallback`. В нем предполагается наличие глобальной строковой переменной с именем `response`, в которой хранится полученная строка, и глобального экземпляра класса **ManualResetEvent** с именем `receiveDone`. Для завершения сетевого сеанса сервер должен завершить работу сокета клиента надлежащим образом.  
  
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
  
## <a name="see-also"></a>См. также

- [Использование синхронного сокета клиента](using-a-synchronous-client-socket.md)
- [Прослушивание с помощью сокетов](listening-with-sockets.md)
- [Примеры асинхронных сокетов клиента](asynchronous-client-socket-example.md)
