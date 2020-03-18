---
title: Использование служб UDP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- protocols, UDP
- network resources, UDP
- requesting data from Internet, UDP
- UDP
- receiving data, UDP
- Internet, UDP
- broadcasting messages to multiple addresses
- data requests, UDP
- UdpClient class, about UdpClient class
- sending data, UDP
- application protocols, UDP
ms.assetid: d5c3477a-e798-454c-a890-738ba14c5707
ms.openlocfilehash: 477095ada6e44f66cbc60cd80375da9a87f38e39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180608"
---
# <a name="using-udp-services"></a>Использование служб UDP
Класс <xref:System.Net.Sockets.UdpClient> взаимодействует с сетевыми службами по протоколу UDP. Методы и свойства класса <xref:System.Net.Sockets.UdpClient> абстрагируют сведения о создании <xref:System.Net.Sockets.Socket> для запроса и получения данных по протоколу UDP.

UDP — это простой протокол для максимально эффективной передачи данных в удаленный узел. Однако поскольку протокол UDP не предусматривает установление соединений, доставка датаграмм UDP, отправляемых в удаленную конечную точку, не гарантируется. Кроме того, не гарантируется их доставка в той же очередности, в которой они отправлялись. Приложения, использующие протокол UDP, должны быть готовы обрабатывать отсутствующие, повторяющиеся и идущие не по порядку датаграммы.

Чтобы отправить датаграмму по протоколу UDP, необходимо знать адрес сетевого устройства, в котором размещается нужная служба, и номер порта UDP, который служба использует для обмена данными. Номера портов для основных служб определяются организацией IANA ("Администрация адресного пространства Интернет"). См. документ [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Реестр названий служб и номеров портов транспортных протоколов). Службы, отсутствующие в списке IANA, могут иметь номера портов в диапазоне от 1024 до 65535.

Для поддержки широковещательных сообщений UDP в IP-сетях используются специальные сетевые адреса. Далее в качестве примера используется семейство адресов IP версии 4.

В IP версии 4 для указания сетевых адресов используются 32 бита. Для адресов класса C с маской сети 255.255.255.0 эти биты разделяются на четыре октета. В десятичной форме эти четыре октета образуют знакомую нотацию с использованием четырех чисел, разделенных точками, например 192.168.100.2. Первые два октета (192.168 в этом примере) — это номер сети, третий октет (100) — это подсеть, а последний октет (2) — идентификатор узла.

Если задать все биты IP-адреса равными единице (то есть 255.255.255.255 в десятичной форме), получится ограниченный широковещательный адрес. При отправке датаграммы UDP на этот адрес сообщение доставляется всем узлам в сегменте локальной сети. Так как маршрутизаторы никогда не перенаправляют сообщения, отправляемые на этот адрес, широковещательное сообщение получают только узлы в этом сегменте сети.

Для направления широковещательных сообщений в определенные части сети можно задать все биты идентификатора узла. Например, для отправки широковещательного сообщения всем узлам в сети, которая определяется IP-адресами, начинающимися с 192.168.1, используйте адрес 192.168.1.255.

В приведенном ниже примере кода используется объект <xref:System.Net.Sockets.UdpClient> для прослушивания датаграмм UDP через порт 11000. Клиент получает строку сообщения и выводит сообщение в консоли.

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class UDPListener
   Private Const listenPort As Integer = 11000

   Private Shared Sub StartListener()
      Dim listener As New UdpClient(listenPort)
      Dim groupEP As New IPEndPoint(IPAddress.Any, listenPort)
      Try
         While True
            Console.WriteLine("Waiting for broadcast")
            Dim bytes As Byte() = listener.Receive(groupEP)
            Console.WriteLine("Received broadcast from {0} :", groupEP)
            Console.WriteLine(Encoding.ASCII.GetString(bytes, 0, bytes.Length))
         End While
      Catch e As SocketException
         Console.WriteLine(e)
      Finally
         listener.Close()
      End Try
   End Sub 'StartListener

   Public Shared Sub Main()
      StartListener()
   End Sub 'Main
End Class 'UDPListener
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

public class UDPListener
{
    private const int listenPort = 11000;

    private static void StartListener()
    {
        UdpClient listener = new UdpClient(listenPort);
        IPEndPoint groupEP = new IPEndPoint(IPAddress.Any, listenPort);

        try
        {
            while (true)
            {
                Console.WriteLine("Waiting for broadcast");
                byte[] bytes = listener.Receive(ref groupEP);

                Console.WriteLine($"Received broadcast from {groupEP} :");
                Console.WriteLine($" {Encoding.ASCII.GetString(bytes, 0, bytes.Length)}");
            }
        }
        catch (SocketException e)
        {
            Console.WriteLine(e);
        }
        finally
        {
            listener.Close();
        }
    }

    public static void Main()
    {
        StartListener();
    }
}
```

В приведенном ниже примере кода используется объект <xref:System.Net.Sockets.Socket> для отправки датаграмм UDP на направленный широковещательный адрес 192.168.1.255 через порт 11000. Клиент отправляет строку сообщения, указанную в командной строке.

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class Program
    Public Shared Sub Main(args() As [String])
      Dim s As New Socket(AddressFamily.InterNetwork, SocketType.Dgram, ProtocolType.Udp)
      Dim broadcast As IPAddress = IPAddress.Parse("192.168.1.255")
      Dim sendbuf As Byte() = Encoding.ASCII.GetBytes(args(0))
      Dim ep As New IPEndPoint(broadcast, 11000)
      s.SendTo(sendbuf, ep)
      Console.WriteLine("Message sent to the broadcast address")
   End Sub 'Main
End Class
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

class Program
{
    static void Main(string[] args)
    {
        Socket s = new Socket(AddressFamily.InterNetwork, SocketType.Dgram, ProtocolType.Udp);

        IPAddress broadcast = IPAddress.Parse("192.168.1.255");

        byte[] sendbuf = Encoding.ASCII.GetBytes(args[0]);
        IPEndPoint ep = new IPEndPoint(broadcast, 11000);

        s.SendTo(sendbuf, ep);

        Console.WriteLine("Message sent to the broadcast address");
    }
}
```

## <a name="see-also"></a>См. также раздел

- <xref:System.Net.Sockets.UdpClient>
- <xref:System.Net.IPAddress>
