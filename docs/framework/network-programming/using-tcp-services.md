---
title: "Использование служб TCP | Microsoft Docs"
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
  - "запрос данных из Интернета, TCP"
  - "получение данных, TCP"
  - "класс TcpClient, сведения о классе TcpClient"
  - "запросы данных, TCP"
  - "протоколы приложений, TCP"
  - "сетевые ресурсы, TCP"
  - "отправка данных, TCP"
  - "TCP"
  - "протоколы, TCP"
  - "Интернет, TCP"
ms.assetid: d2811830-3bcb-495c-b82d-cda9cf919aad
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Использование служб TCP
Класс <xref:System.Net.Sockets.TcpClient> запрашивает данные из ресурса в интернете по протоколу TCP.  Методы и свойства **TcpClient** резюмируют сведения для создания <xref:System.Net.Sockets.Socket> для запроса и получения данных по протоколу TCP.  Поскольку подключение к удаленному устройство представлено в виде потока, данные можно считывать и записывать с платформой .NET Framework поток\- методы обработки.  
  
 Протокол TCP устанавливает соединение с удаленной конечной точкой, а затем пользами, соединение отправлять и получать пакеты данных.  Протокол TCP отвечает за обеспечение, что пакеты данных отправлены к конечной точке, и сборка, когда они поступают в правильном порядке.  
  
 Чтобы установить подключение TCP, необходимо знать адрес устройства сети при размещении службы, и необходимо знать TCP\-порт, служба использует для обмена данными.  Internet Assigned Numbers Authority \(Iana\) определяет номер порта для общих служб \(см. раздел www.iana.org\/assignments\/port\-numbers\).  Службы не в списке Iana могут иметь номера портов в диапазоне от 1.024 до 65.535.  
  
 В следующем примере показано, как настраивать **TcpClient** для подключения к серверу времени на TCP\-порт 13.  
  
```vb  
Imports System  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class TcpTimeClient  
    Private const portNum As Integer = 13  
    Private const hostName As String = "host.contoso.com"  
  
    ' Entry point  that delegates to C-style main Private Function.  
    Public Overloads Shared Sub Main()  
        System.Environment.ExitCode = _  
            Main(System.Environment.GetCommandLineArgs())  
    End Sub  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
        Try  
            Dim client As New TcpClient(hostName, portNum)  
  
            Dim ns As NetworkStream = client.GetStream()  
  
            Dim bytes(1024) As Byte  
            Dim bytesRead As Integer = ns.Read(bytes, 0, bytes.Length)  
  
            Console.WriteLine(Encoding.ASCII.GetString(bytes, 0, bytesRead))  
  
        Catch e As Exception  
            Console.WriteLine(e.ToString())  
        End Try  
  
        client.Close()  
  
        Return 0  
    End Function 'Main  
End Class 'TcpTimeClient  
  
```  
  
```csharp  
using System;  
using System.Net.Sockets;  
using System.Text;  
  
public class TcpTimeClient {  
    private const int portNum = 13;  
    private const string hostName = "host.contoso.com";  
  
    public static int Main(String[] args) {  
        try {  
            TcpClient client = new TcpClient(hostName, portNum);  
  
            NetworkStream ns = client.GetStream();  
  
            byte[] bytes = new byte[1024];  
            int bytesRead = ns.Read(bytes, 0, bytes.Length);  
  
            Console.WriteLine(Encoding.ASCII.GetString(bytes,0,bytesRead));  
  
            client.Close();  
  
        } catch (Exception e) {  
            Console.WriteLine(e.ToString());  
        }  
  
        return 0;  
    }  
}  
```  
  
 <xref:System.Net.Sockets.TcpListener> используется для контроля портов для входящих запросов, а затем создать или **Сокет** или **TcpClient**, которое управляет подключением клиенту.  Метод <xref:System.Net.Sockets.TcpListener.Start%2A> входит прослушивание, а метод <xref:System.Net.Sockets.TcpListener.Stop%2A> отключить прослушивание порта.  Метод <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> принимает запросы входящего подключения и создает **TcpClient** для обработки запроса, а метод <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> принимает запросы входящего подключения и создает **Сокет** для обработки запроса.  
  
 В следующем примере показано создание сервер времени сети с помощью монитора **TcpListener** на TCP\-порт 13.  При получении запроса входящего подключения, сервер отвечает времени текущей датой и временем из хоста\-сервера.  
  
```vb  
Imports System  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class TcpTimeServer  
  
    Private const portNum As Integer = 13  
  
    ' Entry point that delegates to C-style main Private Function.  
    Public Overloads Shared Sub Main()  
        System.Environment.ExitCode = _  
            Main(System.Environment.GetCommandLineArgs())  
    End Sub  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
        Dim done As Boolean = False  
  
        Dim listener As New TcpListener(portNum)  
  
        listener.Start()  
  
        While Not done  
            Console.Write("Waiting for connection...")  
            Dim client As TcpClient = listener.AcceptTcpClient()  
  
            Console.WriteLine("Connection accepted.")  
            Dim ns As NetworkStream = client.GetStream()  
  
            Dim byteTime As Byte() = _  
                Encoding.ASCII.GetBytes(DateTime.Now.ToString())  
  
            Try  
                ns.Write(byteTime, 0, byteTime.Length)  
                ns.Close()  
                client.Close()  
            Catch e As Exception  
                Console.WriteLine(e.ToString())  
            End Try  
        End While  
  
        listener.Stop()  
  
        Return 0  
    End Function 'Main  
End Class 'TcpTimeServer  
```  
  
```csharp  
using System;  
using System.Net.Sockets;  
using System.Text;  
  
public class TcpTimeServer {  
  
    private const int portNum = 13;  
  
    public static int Main(String[] args) {  
        bool done = false;  
  
        TcpListener listener = new TcpListener(portNum);  
  
        listener.Start();  
  
        while (!done) {  
            Console.Write("Waiting for connection...");  
            TcpClient client = listener.AcceptTcpClient();  
  
            Console.WriteLine("Connection accepted.");  
            NetworkStream ns = client.GetStream();  
  
            byte[] byteTime = Encoding.ASCII.GetBytes(DateTime.Now.ToString());  
  
            try {  
                ns.Write(byteTime, 0, byteTime.Length);  
                ns.Close();  
                client.Close();  
            } catch (Exception e) {  
                Console.WriteLine(e.ToString());  
            }  
        }  
  
        listener.Stop();  
  
        return 0;  
    }  
  
}  
```  
  
## См. также  
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)