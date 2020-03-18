---
title: Использование сокетов клиента
ms.date: 03/30/2017
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
ms.openlocfilehash: fe2ad55c3f60347369c0e92bc834d81d98f3870e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71046957"
---
# <a name="using-client-sockets"></a><span data-ttu-id="64f3f-102">Использование сокетов клиента</span><span class="sxs-lookup"><span data-stu-id="64f3f-102">Using Client Sockets</span></span>
<span data-ttu-id="64f3f-103">Перед инициацией взаимодействия через <xref:System.Net.Sockets.Socket> необходимо создать канал передачи данных между приложением и удаленным устройством.</span><span class="sxs-lookup"><span data-stu-id="64f3f-103">Before you can initiate a conversation through a <xref:System.Net.Sockets.Socket>, you must create a data pipe between your application and the remote device.</span></span> <span data-ttu-id="64f3f-104">В этом примере показано, как создать подключение TCP/IP к удаленном устройству (хотя существуют и другие семейства сетевых адресов и протоколы).</span><span class="sxs-lookup"><span data-stu-id="64f3f-104">Although other network address families and protocols exist, this example shows how to create a TCP/IP connection to a remote service.</span></span>  
  
 <span data-ttu-id="64f3f-105">В качестве уникального идентификатора службы протокол TCP/IP использует сетевой адрес и номер порта службы.</span><span class="sxs-lookup"><span data-stu-id="64f3f-105">TCP/IP uses a network address and a service port number to uniquely identify a service.</span></span> <span data-ttu-id="64f3f-106">Сетевой адрес определяет конкретное устройство в сети, а номер порта — службу на этом устройстве, к которой необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="64f3f-106">The network address identifies a specific device on the network; the port number identifies the specific service on that device to connect to.</span></span> <span data-ttu-id="64f3f-107">Сочетание сетевого адреса и порта службы называется конечной точкой. Она представлена в платформе .NET Framework классом <xref:System.Net.EndPoint>.</span><span class="sxs-lookup"><span data-stu-id="64f3f-107">The combination of network address and service port is called an endpoint, which is represented in the .NET Framework by the <xref:System.Net.EndPoint> class.</span></span> <span data-ttu-id="64f3f-108">Для каждого поддерживаемого семейства адресов определен потомок **EndPoint**. Для семейства IP-адресов это класс <xref:System.Net.IPEndPoint>.</span><span class="sxs-lookup"><span data-stu-id="64f3f-108">A descendant of **EndPoint** is defined for each supported address family; for the IP address family, the class is <xref:System.Net.IPEndPoint>.</span></span>  
  
 <span data-ttu-id="64f3f-109">Класс <xref:System.Net.Dns> предоставляет службы доменных имен (DNS) для приложений, использующих интернет-службы TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="64f3f-109">The <xref:System.Net.Dns> class provides domain-name services to applications that use TCP/IP Internet services.</span></span> <span data-ttu-id="64f3f-110">Метод <xref:System.Net.Dns.Resolve%2A> отправляет DNS-серверу запрос на сопоставление понятного доменного имени (например, host.contoso.com) с адресом в Интернете в числовой форме (например, 192.168.1.1).</span><span class="sxs-lookup"><span data-stu-id="64f3f-110">The <xref:System.Net.Dns.Resolve%2A> method queries a DNS server to map a user-friendly domain name (such as "host.contoso.com") to a numeric Internet address (such as 192.168.1.1).</span></span> <span data-ttu-id="64f3f-111">Метод **Resolve** возвращает объект <xref:System.Net.IPHostEntry>, который содержит список адресов и псевдонимов, соответствующих запрошенному имени.</span><span class="sxs-lookup"><span data-stu-id="64f3f-111">**Resolve** returns an <xref:System.Net.IPHostEntry> that contains a list of addresses and aliases for the requested name.</span></span> <span data-ttu-id="64f3f-112">В большинстве случаев можно использовать первый адрес из возвращенного массива <xref:System.Net.IPHostEntry.AddressList%2A>.</span><span class="sxs-lookup"><span data-stu-id="64f3f-112">In most cases, you can use the first address returned in the <xref:System.Net.IPHostEntry.AddressList%2A> array.</span></span> <span data-ttu-id="64f3f-113">Приведенный ниже код получает объект <xref:System.Net.IPAddress>, содержащий IP-адрес сервера host.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="64f3f-113">The following code gets an <xref:System.Net.IPAddress> containing the IP address for the server host.contoso.com.</span></span>  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 <span data-ttu-id="64f3f-114">Номера портов для основных служб определяются организацией IANA ("Администрация адресного пространства Интернет"). Дополнительные сведения см. в документе [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Реестр названий служб и номеров портов транспортных протоколов).</span><span class="sxs-lookup"><span data-stu-id="64f3f-114">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (for more information, see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span></span> <span data-ttu-id="64f3f-115">Другие службы могут использовать номера портов в диапазоне от 1024 до 65535.</span><span class="sxs-lookup"><span data-stu-id="64f3f-115">Other services can have registered port numbers in the range 1,024 to 65,535.</span></span> <span data-ttu-id="64f3f-116">Приведенный ниже код объединяет IP-адрес сервера host.contoso.com с номером порта для формирования удаленной конечной точки, к которой необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="64f3f-116">The following code combines the IP address for host.contoso.com with a port number to create a remote endpoint for a connection.</span></span>  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 <span data-ttu-id="64f3f-117">Определив адрес удаленного устройства и выбрав порт для подключения, приложение может попытаться установить соединение с удаленным устройством.</span><span class="sxs-lookup"><span data-stu-id="64f3f-117">After determining the address of the remote device and choosing a port to use for the connection, the application can attempt to establish a connection with the remote device.</span></span> <span data-ttu-id="64f3f-118">В приведенном ниже примере существующий объект **IPEndPoint** используется для подключения к удаленному устройству. Кроме того, перехватываются все возникающие исключения.</span><span class="sxs-lookup"><span data-stu-id="64f3f-118">The following example uses an existing **IPEndPoint** to connect to a remote device and catches any exceptions that are thrown.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64f3f-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="64f3f-119">See also</span></span>

- [<span data-ttu-id="64f3f-120">Использование синхронного сокета клиента</span><span class="sxs-lookup"><span data-stu-id="64f3f-120">Using a Synchronous Client Socket</span></span>](using-a-synchronous-client-socket.md)
- [<span data-ttu-id="64f3f-121">Использование асинхронных сокетов клиента</span><span class="sxs-lookup"><span data-stu-id="64f3f-121">Using an Asynchronous Client Socket</span></span>](using-an-asynchronous-client-socket.md)
- [<span data-ttu-id="64f3f-122">Практическое руководство. Создание сокета</span><span class="sxs-lookup"><span data-stu-id="64f3f-122">How to: Create a Socket</span></span>](how-to-create-a-socket.md)
- [<span data-ttu-id="64f3f-123">Сокеты</span><span class="sxs-lookup"><span data-stu-id="64f3f-123">Sockets</span></span>](sockets.md)
