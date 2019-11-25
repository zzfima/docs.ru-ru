---
title: Использование служб TCP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- requesting data from Internet, TCP
- receiving data, TCP
- TcpClient class, about TcpClient class
- data requests, TCP
- application protocols, TCP
- network resources, TCP
- sending data, TCP
- TCP
- protocols, TCP
- Internet, TCP
ms.assetid: d2811830-3bcb-495c-b82d-cda9cf919aad
ms.openlocfilehash: 3678586647dcf9c47b4494197fbf56cab865b3d3
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039493"
---
# <a name="using-tcp-services"></a>Использование служб TCP

Класс <xref:System.Net.Sockets.TcpClient> запрашивает данные из ресурса в Интернете по протоколу TCP. Методы и свойства **TcpClient** абстрагируют сведения для создания <xref:System.Net.Sockets.Socket> с целью запроса и получения данных по протоколу TCP. Так как подключение к удаленному устройству представлено в виде потока, данные можно считывать и записывать с помощью методов работы с потоками платформы .NET Framework.

Протокол TCP устанавливает соединение с удаленной конечной точкой, а затем использует его для отправки и получения пакетов данных. Протокол TCP отвечает за отправку пакетов данных в конечную точку и их сборку в правильном порядке после доставки.

Чтобы установить подключение TCP, необходимо знать адрес сетевого устройства, в котором размещается нужная служба, и порт TCP, который служба использует для обмена данными. Номера портов для основных служб определяются организацией IANA ("Администрация адресного пространства Интернет"). См. документ [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Реестр названий служб и номеров портов транспортных протоколов). Службы, отсутствующие в списке IANA, могут иметь номера портов в диапазоне от 1024 до 65535.

В приведенном ниже примере показано, как настроить **TcpClient** для подключения к серверу времени через порт TCP 13:

```vb
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

    Overloads Public Shared Function Main(args As String()) As Integer
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
    End Function
End Class
```

```csharp
using System;
using System.Net.Sockets;
using System.Text;

public class TcpTimeClient
{
    private const int portNum = 13;
    private const string hostName = "host.contoso.com";

    public static int Main(String[] args)
    {
        try
        {
            var client = new TcpClient(hostName, portNum);

            NetworkStream ns = client.GetStream();

            byte[] bytes = new byte[1024];
            int bytesRead = ns.Read(bytes, 0, bytes.Length);

            Console.WriteLine(Encoding.ASCII.GetString(bytes,0,bytesRead));

            client.Close();

        }
        catch (Exception e)
        {
            Console.WriteLine(e.ToString());
        }

        return 0;
    }
}
```

<xref:System.Net.Sockets.TcpListener> используется для отслеживания входящих запросов на порте и последующего создания объекта **Socket** или **TcpClient**, который управляет подключением к клиенту. Метод <xref:System.Net.Sockets.TcpListener.Start%2A> включает прослушивание порта, а метод <xref:System.Net.Sockets.TcpListener.Stop%2A> отключает его. Метод <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> принимает входящие запросы на подключение и создает **TcpClient** для их обработки, а метод <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> делает то же самое, но создает **Socket**.

В приведенном ниже примере показано создание сервера времени в сети с использованием **TcpListener** для наблюдения за портом TCP 13. При получении входящего запроса на подключение сервер времени сообщает в ответ текущую дату и время с сервера узла.

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class TcpTimeServer

    Private const portNum As Integer = 13

    ' Entry point that delegates to C-style main Private Function.
    Public Overloads Shared Sub Main()
        System.Environment.ExitCode = _
            Main(System.Environment.GetCommandLineArgs())
    End Sub

    Overloads Public Shared Function Main(args As String()) As Integer
        Dim done As Boolean = False

        Dim listener As New TcpListener(IPAddress.Any, portNum)

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
    End Function
End Class
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

public class TcpTimeServer
{

    private const int portNum = 13;

    public static int Main(String[] args)
    {
        bool done = false;

        var listener = new TcpListener(IPAddress.Any, portNum);

        listener.Start();

        while (!done)
        {
            Console.Write("Waiting for connection...");
            TcpClient client = listener.AcceptTcpClient();

            Console.WriteLine("Connection accepted.");
            NetworkStream ns = client.GetStream();

            byte[] byteTime = Encoding.ASCII.GetBytes(DateTime.Now.ToString());

            try
            {
                ns.Write(byteTime, 0, byteTime.Length);
                ns.Close();
                client.Close();
            }
            catch (Exception e)
            {
                Console.WriteLine(e.ToString());
            }
        }

        listener.Stop();

        return 0;
    }

}
```
