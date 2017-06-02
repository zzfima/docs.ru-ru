---
title: "Использование служб UDP | Microsoft Docs"
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
  - "протоколы, UDP"
  - "сетевые ресурсы, UDP"
  - "запрос данных из Интернета, UDP"
  - "UDP"
  - "получение данных, UDP"
  - "Интернет, UDP"
  - "широковещательная рассылка сообщений по нескольким адресам"
  - "запросы данных, UDP"
  - "класс UdpClient, сведения о классе UdpClient"
  - "отправка данных, UDP"
  - "протоколы приложений, UDP"
ms.assetid: d5c3477a-e798-454c-a890-738ba14c5707
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Использование служб UDP
Класс <xref:System.Net.Sockets.UdpClient> взаимодействует с сетевыми службами, используя UDP.  Свойства и методы класса <xref:System.Net.Sockets.UdpClient> резюмируют сведения для создания <xref:System.Net.Sockets.Socket> для запроса и получения данных с помощью UDP.  
  
 UDP \(UDP\) простой протокол, который позволяет лучше всего причина доставки данных на удаленный узел.  Однако поскольку протокол UDP connectionless протокол, не гарантированно прибывают UDP, отправляемые датаграммы к удаленной конечной точке, и они гарантировали для прибытия в одну и ту же последовательность, в которой они отправлены.  Приложения, использующие протокол UDP необходимо подготовить для обработки отсутствует, дубликат и датаграмм вне последовательности.  
  
 Отправить датаграмма с помощью UDP, необходимо знать сетевой адрес устройства сети при размещении службы и номер порта UDP, служба использует для обмена данными.  Internet Assigned Numbers Authority \(Iana\) определяет номер порта для общих служб \(см. раздел www.iana.org\/assignments\/port\-numbers\).  Службы не в списке Iana могут иметь номера портов в диапазоне от 1.024 до 65.535.  
  
 Специальные сетевого адреса используются для поддержки широковещательные сообщения UDP на основе IP сетях.  Следующее обсуждение использует семейство адресов версии 4 протокола IP, используемое в Интернете в качестве примера.  
  
 Адреса IP версии 4 использует 32 бита, чтобы указать сетевой адрес.  Для адресов C\# класса с помощью netmask 255.255.255.0, эти биты разделяются на 4 октета.  Выражанный в десятичном числе, 4 формируют знакомую октета нотации ставить точки\- квартета, например 192.168.100.2.  Первые 2 192,168 октета \(в данном примере\) формируют номер сети, третий октет \(100\) определяют подсеть и конечный октет \(2\) идентификатор основного приложения.  
  
 Установка все биты IP\-адрес, 255.255.255.255, ограниченный или формы адрес широковещательной рассылки.  Отправляет датаграмму UDP к этому адресу доставляет сообщение любому узлу в сегменте локальной сети.  Поскольку сообщения, отправляемые по этому адресу, только основные приложения никогда front маршрутизаторов на сегмент сети, получают широковещательное сообщение.  
  
 Широковещательные можно непосредственно к определенным фрагментам сети, задав все биты идентификатора основного приложения.  Например, чтобы отправить широковещательной ко всем основным приложениям в сети IP\-адресами, начиная с указанной 192.168.1, используйте адрес 192.168.1.255.  
  
 В следующем примере кода используется <xref:System.Net.Sockets.UdpClient> для прослушивания датаграмм UDP, отправляемых непосредственно широковещательному адресу 192.168.1.255 на порту 11.000.  Клиент получает строку сообщения и записывает сообщение на консоль.  
  
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
  
 В следующем примере кода используется <xref:System.Net.Sockets.UdpClient> отправить датаграммы UDP значение прямой широковещательному адресу 192.168.1.255, используя порт 11.000.  Клиент отправляет строку сообщения, указанную в командной строке.  
  
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
  
## См. также  
 <xref:System.Net.Sockets.UdpClient>   
 <xref:System.Net.IPAddress>   
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)