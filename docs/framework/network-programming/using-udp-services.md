---
title: "Использование служб UDP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 86f44c5aa4c744ab6966f0cb6b3834dd1f5f0f48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-udp-services"></a>Использование служб UDP
Класс <xref:System.Net.Sockets.UdpClient> взаимодействует с сетевыми службами по протоколу UDP. Методы и свойства класса <xref:System.Net.Sockets.UdpClient> абстрагируют сведения о создании <xref:System.Net.Sockets.Socket> для запроса и получения данных по протоколу UDP.  
  
 UDP — это простой протокол для максимально эффективной передачи данных в удаленный узел. Однако поскольку протокол UDP не предусматривает установление соединений, доставка датаграмм UDP, отправляемых в удаленную конечную точку, не гарантируется. Кроме того, не гарантируется их доставка в той же очередности, в которой они отправлялись. Приложения, использующие протокол UDP, должны быть готовы обрабатывать отсутствующие, повторяющиеся и идущие не по порядку датаграммы.  
  
 Чтобы отправить датаграмму по протоколу UDP, необходимо знать адрес сетевого устройства, в котором размещается нужная служба, и номер порта UDP, который служба использует для обмена данными. Номера портов для основных служб определяются организацией IANA (Администрация адресного пространства Интернет). См. страницу www.iana.org/assignments/port-numbers. Службы, отсутствующие в списке IANA, могут иметь номера портов в диапазоне от 1024 до 65535.  
  
 Для поддержки широковещательных сообщений UDP в IP-сетях используются специальные сетевые адреса. Далее в качестве примера используется семейство адресов IP версии 4.  
  
 В IP версии 4 для указания сетевых адресов используются 32 бита. Для адресов класса C с маской сети 255.255.255.0 эти биты разделяются на четыре октета. В десятичной форме эти четыре октета образуют знакомую нотацию с использованием четырех чисел, разделенных точками, например 192.168.100.2. Первые два октета (192.168 в этом примере) — это номер сети, третий октет (100) — это подсеть, а последний октет (2) — идентификатор узла.  
  
 Если задать все биты IP-адреса равными единице (то есть 255.255.255.255 в десятичной форме), получится ограниченный широковещательный адрес. При отправке датаграммы UDP на этот адрес сообщение доставляется всем узлам в сегменте локальной сети. Так как маршрутизаторы никогда не перенаправляют сообщения, отправляемые на этот адрес, широковещательное сообщение получают только узлы в этом сегменте сети.  
  
 Для направления широковещательных сообщений в определенные части сети можно задать все биты идентификатора узла. Например, для отправки широковещательного сообщения всем узлам в сети, которая определяется IP-адресами, начинающимися с 192.168.1, используйте адрес 192.168.1.255.  
  
 В приведенном ниже примере кода используется объект <xref:System.Net.Sockets.UdpClient> для прослушивания датаграмм UDP, отправляемых на направленный широковещательный адрес 192.168.1.255 через порт 11000. Клиент получает строку сообщения и выводит сообщение в консоли.  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class UDPListener  
   Private Const listenPort As Integer = 11000  
  
   Private Shared Sub StartListener()  
      Dim done As Boolean = False  
      Dim listener As New UdpClient(listenPort)  
      Dim groupEP As New IPEndPoint(IPAddress.Any, listenPort)  
      Try  
         While Not done  
            Console.WriteLine("Waiting for broadcast")  
            Dim bytes As Byte() = listener.Receive(groupEP)  
            Console.WriteLine("Received broadcast from {0} :", _  
                groupEP.ToString())   
            Console.WriteLine( _  
                Encoding.ASCII.GetString(bytes, 0, bytes.Length))  
            Console.WriteLine()  
         End While  
      Catch e As Exception  
         Console.WriteLine(e.ToString())  
      Finally  
         listener.Close()  
      End Try  
   End Sub 'StartListener  
  
   Public Shared Function Main() As Integer  
      StartListener()  
      Return 0  
   End Function 'Main  
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
        bool done = false;  
  
        UdpClient listener = new UdpClient(listenPort);  
        IPEndPoint groupEP = new IPEndPoint(IPAddress.Any,listenPort);  
  
        try   
        {  
            while (!done)   
            {  
                Console.WriteLine("Waiting for broadcast");  
                byte[] bytes = listener.Receive( ref groupEP);  
  
                Console.WriteLine("Received broadcast from {0} :\n {1}\n",  
                    groupEP.ToString(),  
                    Encoding.ASCII.GetString(bytes,0,bytes.Length));  
            }  
  
        }   
        catch (Exception e)   
        {  
            Console.WriteLine(e.ToString());  
        }  
        finally  
        {  
            listener.Close();  
        }  
    }  
  
    public static int Main()   
    {  
        StartListener();  
  
        return 0;  
    }  
}  
```  
  
 В приведенном ниже примере кода используется объект <xref:System.Net.Sockets.UdpClient> для отправки датаграмм UDP на направленный широковещательный адрес 192.168.1.255 через порт 11000. Клиент отправляет строку сообщения, указанную в командной строке.  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class Program  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
      Dim s As New Socket(AddressFamily.InterNetwork, SocketType.Dgram,  
          ProtocolType.Udp)  
      Dim broadcast As IPAddress = IPAddress.Parse("192.168.1.255")  
      Dim sendbuf As Byte() = Encoding.ASCII.GetBytes(args(0))  
      Dim ep As New IPEndPoint(broadcast, 11000)  
      s.SendTo(sendbuf, ep)  
      Console.WriteLine("Message sent to the broadcast address")  
   End Function 'Main  
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
        Socket s = new Socket(AddressFamily.InterNetwork, SocketType.Dgram,  
            ProtocolType.Udp);  
  
        IPAddress broadcast = IPAddress.Parse("192.168.1.255");  
  
        byte[] sendbuf = Encoding.ASCII.GetBytes(args[0]);  
        IPEndPoint ep = new IPEndPoint(broadcast, 11000);  
  
        s.SendTo(sendbuf, ep);  
  
        Console.WriteLine("Message sent to the broadcast address");  
    }  
}  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.Sockets.UdpClient>  
 <xref:System.Net.IPAddress>  
 
