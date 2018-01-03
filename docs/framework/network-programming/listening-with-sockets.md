---
title: "прослушивание с помощью сокетов"
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
- sockets, listening with sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- protocols, sockets
- listening with sockets
- Internet, sockets
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 6b799f57644420653b371ac0e65b414c807008b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="listening-with-sockets"></a><span data-ttu-id="5efe9-102">прослушивание с помощью сокетов</span><span class="sxs-lookup"><span data-stu-id="5efe9-102">Listening with Sockets</span></span>
<span data-ttu-id="5efe9-103">Сокеты прослушивателя и сервера открывают порт в сети и ожидают, когда клиент подключится к этому порту.</span><span class="sxs-lookup"><span data-stu-id="5efe9-103">Listener or server sockets open a port on the network and then wait for a client to connect to that port.</span></span> <span data-ttu-id="5efe9-104">В этом примере показано, как создать удаленную службу для сети TCP/IP (хотя существуют и другие семейства сетевых адресов и протоколов).</span><span class="sxs-lookup"><span data-stu-id="5efe9-104">Although other network address families and protocols exist, this example shows how to create remote service for a TCP/IP network.</span></span>  
  
 <span data-ttu-id="5efe9-105">Уникальный адрес службы TCP/IP определяется сочетанием IP-адреса узла и номера порта службы, которые используются при создании конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="5efe9-105">The unique address of a TCP/IP service is defined by combining the IP address of the host with the port number of the service to create an endpoint for the service.</span></span> <span data-ttu-id="5efe9-106">Класс <xref:System.Net.Dns> предоставляет методы, возвращающие сведения о сетевых адресах, поддерживаемых локальным сетевым устройством.</span><span class="sxs-lookup"><span data-stu-id="5efe9-106">The <xref:System.Net.Dns> class provides methods that return information about the network addresses supported by the local network device.</span></span> <span data-ttu-id="5efe9-107">Если локальное сетевое устройство имеет более одного сетевого адреса или локальная система поддерживает несколько сетевых устройств, класс **Dns** возвращает сведения обо всех сетевых адресах, и приложению необходимо выбрать соответствующий адрес службы.</span><span class="sxs-lookup"><span data-stu-id="5efe9-107">When the local network device has more than one network address, or if the local system supports more than one network device, the **Dns** class returns information about all network addresses, and the application must choose the proper address for the service.</span></span> <span data-ttu-id="5efe9-108">Номера портов для основных служб определяются организацией IANA ("Администрация адресного пространства Интернет"). Дополнительные сведения см. на странице www.iana.org/assignments/port-numbers.</span><span class="sxs-lookup"><span data-stu-id="5efe9-108">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (for more information, see www.iana.org/assignments/port-numbers).</span></span> <span data-ttu-id="5efe9-109">Другие службы могут использовать номера портов в диапазоне от 1024 до 65535.</span><span class="sxs-lookup"><span data-stu-id="5efe9-109">Other services can have registered port numbers in the range 1,024 to 65,535.</span></span>  
  
 <span data-ttu-id="5efe9-110">В следующем примере создается <xref:System.Net.IPEndPoint> для сервера с помощью объединения первого IP-адреса, возвращенного классом **Dns** для компьютера узла, и номера порта, выбранного из диапазона зарегистрированных номеров портов.</span><span class="sxs-lookup"><span data-stu-id="5efe9-110">The following example creates an <xref:System.Net.IPEndPoint> for a server by combining the first IP address returned by **Dns** for the host computer with a port number chosen from the registered port numbers range.</span></span>  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
```  
  
 <span data-ttu-id="5efe9-111">После определения локальной конечной точки необходимо связать <xref:System.Net.Sockets.Socket> с этой конечной точкой с помощью метода <xref:System.Net.Sockets.Socket.Bind%2A> и включить прослушивание для конечной точки с помощью метода <xref:System.Net.Sockets.Socket.Listen%2A>.</span><span class="sxs-lookup"><span data-stu-id="5efe9-111">After the local endpoint is determined, the <xref:System.Net.Sockets.Socket> must be associated with that endpoint using the <xref:System.Net.Sockets.Socket.Bind%2A> method and set to listen on the endpoint using the <xref:System.Net.Sockets.Socket.Listen%2A> method.</span></span> <span data-ttu-id="5efe9-112">Метод **Bind** выдает исключение, если указанное сочетание IP-адреса и порта уже используется.</span><span class="sxs-lookup"><span data-stu-id="5efe9-112">**Bind** throws an exception if the specific address and port combination is already in use.</span></span> <span data-ttu-id="5efe9-113">В следующем примере показано связывание сокета **Socket** с конечной точкой **IPEndPoint**.</span><span class="sxs-lookup"><span data-stu-id="5efe9-113">The following example demonstrates associating a **Socket** with an **IPEndPoint**.</span></span>  
  
```vb  
Dim listener As New Socket(ipAddress.AddressFamily, _  
    SocketType.Stream, ProtocolType.Tcp) 
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
Socket listener = new Socket(ipAddress.AddressFamily,
    SocketType.Stream, ProtocolType.Tcp);
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 <span data-ttu-id="5efe9-114">Метод **Listen** принимает один параметр, который определяет максимальное количество ожидающих подключений для сокета **Socket**. При превышении этого количества клиенту возвращается ошибка "Сервер занят".</span><span class="sxs-lookup"><span data-stu-id="5efe9-114">The **Listen** method takes a single parameter that specifies how many pending connections to the **Socket** are allowed before a server busy error is returned to the connecting client.</span></span> <span data-ttu-id="5efe9-115">В данном случае в очередь на подключение размещается до 100 клиентов. 101 клиенту возвращается ответ "Сервер занят".</span><span class="sxs-lookup"><span data-stu-id="5efe9-115">In this case, up to 100 clients are placed in the connection queue before a server busy response is returned to client number 101.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5efe9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5efe9-116">See Also</span></span>  
 [<span data-ttu-id="5efe9-117">Использование синхронного сокета сервера</span><span class="sxs-lookup"><span data-stu-id="5efe9-117">Using a Synchronous Server Socket</span></span>](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)  
 [<span data-ttu-id="5efe9-118">Использование асинхронных сокетов сервера</span><span class="sxs-lookup"><span data-stu-id="5efe9-118">Using an Asynchronous Server Socket</span></span>](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)  
 [<span data-ttu-id="5efe9-119">Использование сокетов клиента</span><span class="sxs-lookup"><span data-stu-id="5efe9-119">Using Client Sockets</span></span>](../../../docs/framework/network-programming/using-client-sockets.md)  
 [<span data-ttu-id="5efe9-120">Практическое руководство. Создание сокета</span><span class="sxs-lookup"><span data-stu-id="5efe9-120">How to: Create a Socket</span></span>](../../../docs/framework/network-programming/how-to-create-a-socket.md)  
 [<span data-ttu-id="5efe9-121">Сокеты</span><span class="sxs-lookup"><span data-stu-id="5efe9-121">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
