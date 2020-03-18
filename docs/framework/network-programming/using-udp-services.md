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
# <a name="using-udp-services"></a><span data-ttu-id="4a8f3-102">Использование служб UDP</span><span class="sxs-lookup"><span data-stu-id="4a8f3-102">Using UDP Services</span></span>
<span data-ttu-id="4a8f3-103">Класс <xref:System.Net.Sockets.UdpClient> взаимодействует с сетевыми службами по протоколу UDP.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-103">The <xref:System.Net.Sockets.UdpClient> class communicates with network services using UDP.</span></span> <span data-ttu-id="4a8f3-104">Методы и свойства класса <xref:System.Net.Sockets.UdpClient> абстрагируют сведения о создании <xref:System.Net.Sockets.Socket> для запроса и получения данных по протоколу UDP.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-104">The properties and methods of the <xref:System.Net.Sockets.UdpClient> class abstract the details of creating a <xref:System.Net.Sockets.Socket> for requesting and receiving data using UDP.</span></span>

<span data-ttu-id="4a8f3-105">UDP — это простой протокол для максимально эффективной передачи данных в удаленный узел.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-105">User Datagram Protocol (UDP) is a simple protocol that makes a best effort to deliver data to a remote host.</span></span> <span data-ttu-id="4a8f3-106">Однако поскольку протокол UDP не предусматривает установление соединений, доставка датаграмм UDP, отправляемых в удаленную конечную точку, не гарантируется. Кроме того, не гарантируется их доставка в той же очередности, в которой они отправлялись.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-106">However, because the UDP protocol is a connectionless protocol, UDP datagrams sent to the remote endpoint are not guaranteed to arrive, nor are they guaranteed to arrive in the same sequence in which they are sent.</span></span> <span data-ttu-id="4a8f3-107">Приложения, использующие протокол UDP, должны быть готовы обрабатывать отсутствующие, повторяющиеся и идущие не по порядку датаграммы.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-107">Applications that use UDP must be prepared to handle missing, duplicate, and out-of-sequence datagrams.</span></span>

<span data-ttu-id="4a8f3-108">Чтобы отправить датаграмму по протоколу UDP, необходимо знать адрес сетевого устройства, в котором размещается нужная служба, и номер порта UDP, который служба использует для обмена данными.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-108">To send a datagram using UDP, you must know the network address of the network device hosting the service you need and the UDP port number that the service uses to communicate.</span></span> <span data-ttu-id="4a8f3-109">Номера портов для основных служб определяются организацией IANA ("Администрация адресного пространства Интернет"). См. документ [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Реестр названий служб и номеров портов транспортных протоколов).</span><span class="sxs-lookup"><span data-stu-id="4a8f3-109">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span></span> <span data-ttu-id="4a8f3-110">Службы, отсутствующие в списке IANA, могут иметь номера портов в диапазоне от 1024 до 65535.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-110">Services not on the Iana list can have port numbers in the range 1,024 to 65,535.</span></span>

<span data-ttu-id="4a8f3-111">Для поддержки широковещательных сообщений UDP в IP-сетях используются специальные сетевые адреса.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-111">Special network addresses are used to support UDP broadcast messages on IP-based networks.</span></span> <span data-ttu-id="4a8f3-112">Далее в качестве примера используется семейство адресов IP версии 4.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-112">The following discussion uses the IP version 4 address family used on the Internet as an example.</span></span>

<span data-ttu-id="4a8f3-113">В IP версии 4 для указания сетевых адресов используются 32 бита.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-113">IP version 4 addresses use 32 bits to specify a network address.</span></span> <span data-ttu-id="4a8f3-114">Для адресов класса C с маской сети 255.255.255.0 эти биты разделяются на четыре октета.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-114">For class C addresses using a netmask of 255.255.255.0, these bits are separated into four octets.</span></span> <span data-ttu-id="4a8f3-115">В десятичной форме эти четыре октета образуют знакомую нотацию с использованием четырех чисел, разделенных точками, например 192.168.100.2.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-115">When expressed in decimal, the four octets form the familiar dotted-quad notation, such as 192.168.100.2.</span></span> <span data-ttu-id="4a8f3-116">Первые два октета (192.168 в этом примере) — это номер сети, третий октет (100) — это подсеть, а последний октет (2) — идентификатор узла.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-116">The first two octets (192.168 in this example) form the network number, the third octet (100) defines the subnet, and the final octet (2) is the host identifier.</span></span>

<span data-ttu-id="4a8f3-117">Если задать все биты IP-адреса равными единице (то есть 255.255.255.255 в десятичной форме), получится ограниченный широковещательный адрес.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-117">Setting all the bits of an IP address to one, or 255.255.255.255, forms the limited broadcast address.</span></span> <span data-ttu-id="4a8f3-118">При отправке датаграммы UDP на этот адрес сообщение доставляется всем узлам в сегменте локальной сети.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-118">Sending a UDP datagram to this address delivers the message to any host on the local network segment.</span></span> <span data-ttu-id="4a8f3-119">Так как маршрутизаторы никогда не перенаправляют сообщения, отправляемые на этот адрес, широковещательное сообщение получают только узлы в этом сегменте сети.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-119">Because routers never forward messages sent to this address, only hosts on the network segment receive the broadcast message.</span></span>

<span data-ttu-id="4a8f3-120">Для направления широковещательных сообщений в определенные части сети можно задать все биты идентификатора узла.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-120">Broadcasts can be directed to specific portions of a network by setting all bits of the host identifier.</span></span> <span data-ttu-id="4a8f3-121">Например, для отправки широковещательного сообщения всем узлам в сети, которая определяется IP-адресами, начинающимися с 192.168.1, используйте адрес 192.168.1.255.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-121">For example, to send a broadcast to all hosts on the network identified by IP addresses starting with 192.168.1, use the address 192.168.1.255.</span></span>

<span data-ttu-id="4a8f3-122">В приведенном ниже примере кода используется объект <xref:System.Net.Sockets.UdpClient> для прослушивания датаграмм UDP через порт 11000.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-122">The following code example uses a <xref:System.Net.Sockets.UdpClient> to listen for UDP datagrams on port 11,000.</span></span> <span data-ttu-id="4a8f3-123">Клиент получает строку сообщения и выводит сообщение в консоли.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-123">The client receives a message string and writes the message to the console.</span></span>

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

<span data-ttu-id="4a8f3-124">В приведенном ниже примере кода используется объект <xref:System.Net.Sockets.Socket> для отправки датаграмм UDP на направленный широковещательный адрес 192.168.1.255 через порт 11000.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-124">The following code example uses a <xref:System.Net.Sockets.Socket> to send UDP datagrams to the directed broadcast address 192.168.1.255, using port 11,000.</span></span> <span data-ttu-id="4a8f3-125">Клиент отправляет строку сообщения, указанную в командной строке.</span><span class="sxs-lookup"><span data-stu-id="4a8f3-125">The client sends the message string specified on the command line.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4a8f3-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4a8f3-126">See also</span></span>

- <xref:System.Net.Sockets.UdpClient>
- <xref:System.Net.IPAddress>
