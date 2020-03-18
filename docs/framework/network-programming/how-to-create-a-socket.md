---
title: Практическое руководство. Создание сокета
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- Networking
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- Socket class, creating sockets
- Network Resources
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- sockets, creating
ms.assetid: c64a049c-5981-43bc-a2dc-1851473589c7
ms.openlocfilehash: e71e7e235048361580c65bdb551919fe3038130b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180823"
---
# <a name="how-to-create-a-socket"></a><span data-ttu-id="f8e8e-102">Практическое руководство. Создание сокета</span><span class="sxs-lookup"><span data-stu-id="f8e8e-102">How to: Create a Socket</span></span>
<span data-ttu-id="f8e8e-103">Перед использованием сокета для связи с удаленными устройствами необходимо инициализировать сокет, указав протокол и сведения о сетевом адресе.</span><span class="sxs-lookup"><span data-stu-id="f8e8e-103">Before you can use a socket to communicate with remote devices, the socket must be initialized with protocol and network address information.</span></span> <span data-ttu-id="f8e8e-104">Конструктор класса <xref:System.Net.Sockets.Socket> имеет параметры, которые определяют семейство адресов, тип сокета и тип протокола, которые сокет использует для подключения.</span><span class="sxs-lookup"><span data-stu-id="f8e8e-104">The constructor for the <xref:System.Net.Sockets.Socket> class has parameters that specify the address family, socket type, and protocol type that the socket uses to make connections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8e8e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="f8e8e-105">Example</span></span>  
 <span data-ttu-id="f8e8e-106">В следующем примере создается объект Socket, который может использоваться для обмена данными в сетях на основе TCP/IP (например, в Интернете).</span><span class="sxs-lookup"><span data-stu-id="f8e8e-106">The following example creates a Socket that can be used to communicate on a TCP/IP-based network, such as the Internet.</span></span>  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
```  
  
 <span data-ttu-id="f8e8e-107">Чтобы использовать UDP вместо TCP, измените тип протокола, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f8e8e-107">To use UDP instead of TCP, change the protocol type, as in the following example:</span></span>  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
```  
  
 <span data-ttu-id="f8e8e-108">В перечислении <xref:System.Net.Sockets.AddressFamily> указаны стандартные семейства адресов, которые используются классом **Socket** для разрешения сетевых адресов (например, элемент **AddressFamily.InterNetwork** задает семейство адресов протокола IP версии 4).</span><span class="sxs-lookup"><span data-stu-id="f8e8e-108">The <xref:System.Net.Sockets.AddressFamily> enumeration specifies the standard address families used by the **Socket** class to resolve network addresses (for example, the **AddressFamily.InterNetwork** member specifies the IP version 4 address family).</span></span>  
  
 <span data-ttu-id="f8e8e-109">В перечислении <xref:System.Net.Sockets.SocketType> указан тип сокета (например, элемент **SocketType.Stream** указывает стандартный сокет для отправки и получения данных с помощью управления потоком).</span><span class="sxs-lookup"><span data-stu-id="f8e8e-109">The <xref:System.Net.Sockets.SocketType> enumeration specifies the type of socket (for example, the **SocketType.Stream** member indicates a standard socket for sending and receiving data with flow control).</span></span>  
  
 <span data-ttu-id="f8e8e-110">В перечислении <xref:System.Net.Sockets.ProtocolType> указан сетевой протокол, который используется для связи с объектом **Socket** (например, **ProtocolType.Tcp** означает, что сокет использует TCP; **ProtocolType.Udp** означает, что сокет использует UDP).</span><span class="sxs-lookup"><span data-stu-id="f8e8e-110">The <xref:System.Net.Sockets.ProtocolType> enumeration specifies the network protocol to use when communicating on the **Socket** (for example, **ProtocolType.Tcp** indicates that the socket uses TCP; **ProtocolType.Udp** indicates that the socket uses UDP).</span></span>  
  
 <span data-ttu-id="f8e8e-111">После создания объекта **Socket** он может создать подключение к удаленной конечной точке или принимать подключения от удаленных устройств.</span><span class="sxs-lookup"><span data-stu-id="f8e8e-111">After a **Socket** is created, it can either initiate a connection to a remote endpoint or receive connections from remote devices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e8e-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f8e8e-112">See also</span></span>

- [<span data-ttu-id="f8e8e-113">Использование сокетов клиента</span><span class="sxs-lookup"><span data-stu-id="f8e8e-113">Using Client Sockets</span></span>](using-client-sockets.md)
- [<span data-ttu-id="f8e8e-114">Прослушивание с помощью сокетов</span><span class="sxs-lookup"><span data-stu-id="f8e8e-114">Listening with Sockets</span></span>](listening-with-sockets.md)
