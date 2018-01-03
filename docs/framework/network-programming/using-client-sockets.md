---
title: "Использование сокетов клиента"
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
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- Socket class, client sockets
- protocols, sockets
- Internet, sockets
- sockets, client sockets
- client sockets
ms.assetid: 81de9f59-8177-4d98-b25d-43fc32a98383
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 25c033ae46abc65040c00b6beb105c8ebb6b1d90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-client-sockets"></a><span data-ttu-id="d6778-102">Использование сокетов клиента</span><span class="sxs-lookup"><span data-stu-id="d6778-102">Using Client Sockets</span></span>
<span data-ttu-id="d6778-103">Перед инициацией взаимодействия через <xref:System.Net.Sockets.Socket> необходимо создать канал передачи данных между приложением и удаленным устройством.</span><span class="sxs-lookup"><span data-stu-id="d6778-103">Before you can initiate a conversation through a <xref:System.Net.Sockets.Socket>, you must create a data pipe between your application and the remote device.</span></span> <span data-ttu-id="d6778-104">В этом примере показано, как создать подключение TCP/IP к удаленном устройству (хотя существуют и другие семейства сетевых адресов и протоколы).</span><span class="sxs-lookup"><span data-stu-id="d6778-104">Although other network address families and protocols exist, this example shows how to create a TCP/IP connection to a remote service.</span></span>  
  
 <span data-ttu-id="d6778-105">В качестве уникального идентификатора службы протокол TCP/IP использует сетевой адрес и номер порта службы.</span><span class="sxs-lookup"><span data-stu-id="d6778-105">TCP/IP uses a network address and a service port number to uniquely identify a service.</span></span> <span data-ttu-id="d6778-106">Сетевой адрес определяет конкретное устройство в сети, а номер порта — службу на этом устройстве, к которой необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="d6778-106">The network address identifies a specific device on the network; the port number identifies the specific service on that device to connect to.</span></span> <span data-ttu-id="d6778-107">Сочетание сетевого адреса и порта службы называется конечной точкой. Она представлена в платформе .NET Framework классом <xref:System.Net.EndPoint>.</span><span class="sxs-lookup"><span data-stu-id="d6778-107">The combination of network address and service port is called an endpoint, which is represented in the .NET Framework by the <xref:System.Net.EndPoint> class.</span></span> <span data-ttu-id="d6778-108">Для каждого поддерживаемого семейства адресов определен потомок **EndPoint**. Для семейства IP-адресов это класс <xref:System.Net.IPEndPoint>.</span><span class="sxs-lookup"><span data-stu-id="d6778-108">A descendant of **EndPoint** is defined for each supported address family; for the IP address family, the class is <xref:System.Net.IPEndPoint>.</span></span>  
  
 <span data-ttu-id="d6778-109">Класс <xref:System.Net.Dns> предоставляет службы доменных имен (DNS) для приложений, использующих интернет-службы TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="d6778-109">The <xref:System.Net.Dns> class provides domain-name services to applications that use TCP/IP Internet services.</span></span> <span data-ttu-id="d6778-110">Метод <xref:System.Net.Dns.Resolve%2A> отправляет DNS-серверу запрос на сопоставление понятного доменного имени (например, host.contoso.com) с адресом в Интернете в числовой форме (например, 192.168.1.1).</span><span class="sxs-lookup"><span data-stu-id="d6778-110">The <xref:System.Net.Dns.Resolve%2A> method queries a DNS server to map a user-friendly domain name (such as "host.contoso.com") to a numeric Internet address (such as 192.168.1.1).</span></span> <span data-ttu-id="d6778-111">Метод **Resolve** возвращает объект <xref:System.Net.IPHostEntry>, который содержит список адресов и псевдонимов, соответствующих запрошенному имени.</span><span class="sxs-lookup"><span data-stu-id="d6778-111">**Resolve** returns an <xref:System.Net.IPHostEntry> that contains a list of addresses and aliases for the requested name.</span></span> <span data-ttu-id="d6778-112">В большинстве случаев можно использовать первый адрес из возвращенного массива <xref:System.Net.IPHostEntry.AddressList%2A>.</span><span class="sxs-lookup"><span data-stu-id="d6778-112">In most cases, you can use the first address returned in the <xref:System.Net.IPHostEntry.AddressList%2A> array.</span></span> <span data-ttu-id="d6778-113">Приведенный ниже код получает объект <xref:System.Net.IPAddress>, содержащий IP-адрес сервера host.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d6778-113">The following code gets an <xref:System.Net.IPAddress> containing the IP address for the server host.contoso.com.</span></span>  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 <span data-ttu-id="d6778-114">Номера портов для основных служб определяются организацией IANA ("Администрация адресного пространства Интернет"). Дополнительные сведения см. на странице www.iana.org/assignments/port-numbers.</span><span class="sxs-lookup"><span data-stu-id="d6778-114">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (for more information, see www.iana.org/assignments/port-numbers).</span></span> <span data-ttu-id="d6778-115">Другие службы могут использовать номера портов в диапазоне от 1024 до 65535.</span><span class="sxs-lookup"><span data-stu-id="d6778-115">Other services can have registered port numbers in the range 1,024 to 65,535.</span></span> <span data-ttu-id="d6778-116">Приведенный ниже код объединяет IP-адрес сервера host.contoso.com с номером порта для формирования удаленной конечной точки, к которой необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="d6778-116">The following code combines the IP address for host.contoso.com with a port number to create a remote endpoint for a connection.</span></span>  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 <span data-ttu-id="d6778-117">Определив адрес удаленного устройства и выбрав порт для подключения, приложение может попытаться установить соединение с удаленным устройством.</span><span class="sxs-lookup"><span data-stu-id="d6778-117">After determining the address of the remote device and choosing a port to use for the connection, the application can attempt to establish a connection with the remote device.</span></span> <span data-ttu-id="d6778-118">В приведенном ниже примере существующий объект **IPEndPoint** используется для подключения к удаленному устройству. Кроме того, перехватываются все возникающие исключения.</span><span class="sxs-lookup"><span data-stu-id="d6778-118">The following example uses an existing **IPEndPoint** to connect to a remote device and catches any exceptions that are thrown.</span></span>  
  
```vb  
Try  
    s.Connect(ipe)  
Catch ae As ArgumentNullException  
    Console.WriteLine("ArgumentNullException : {0}", _  
        ae.ToString())  
Catch se As SocketException  
    Console.WriteLine("SocketException : {0}", se.ToString())  
Catch e As Exception  
    Console.WriteLine("Unexpected exception : {0}", e.ToString())  
End Try  
```  
  
```csharp  
try {  
    s.Connect(ipe);  
} catch(ArgumentNullException ae) {  
    Console.WriteLine("ArgumentNullException : {0}", ae.ToString());  
} catch(SocketException se) {  
    Console.WriteLine("SocketException : {0}", se.ToString());  
} catch(Exception e) {  
    Console.WriteLine("Unexpected exception : {0}", e.ToString());  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6778-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d6778-119">See Also</span></span>  
 [<span data-ttu-id="d6778-120">Использование синхронного сокета клиента</span><span class="sxs-lookup"><span data-stu-id="d6778-120">Using a Synchronous Client Socket</span></span>](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)  
 [<span data-ttu-id="d6778-121">Использование асинхронных сокетов клиента</span><span class="sxs-lookup"><span data-stu-id="d6778-121">Using an Asynchronous Client Socket</span></span>](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)  
 [<span data-ttu-id="d6778-122">Практическое руководство. Создание сокета</span><span class="sxs-lookup"><span data-stu-id="d6778-122">How to: Create a Socket</span></span>](../../../docs/framework/network-programming/how-to-create-a-socket.md)  
 [<span data-ttu-id="d6778-123">Сокеты</span><span class="sxs-lookup"><span data-stu-id="d6778-123">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
