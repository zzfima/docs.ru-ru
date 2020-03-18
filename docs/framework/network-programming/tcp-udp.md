---
title: TCP-UDP
ms.date: 03/30/2017
helpviewer_keywords:
- protocols, TCP/UDP
- network resources, TCP/UDP
- sending data, TCP/UDP
- TCP/UDP
- TcpClient class, about TcpClient class
- application protocols, TCP/UDP
- receiving data, TCP/UDP
- TcpListener class, about TcpListener class
- Socket class, about Socket class
- UDP
- data requests, TCP/UDP
- requesting data from Internet, TCP/UDP
- Internet, TCP/UDP
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
ms.openlocfilehash: d35278ab7feb42453b5a0adbc86c47b7ac3ff5ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047112"
---
# <a name="tcp-udp"></a><span data-ttu-id="2a2d9-102">TCP-UDP</span><span class="sxs-lookup"><span data-stu-id="2a2d9-102">TCP-UDP</span></span>
<span data-ttu-id="2a2d9-103">Приложения могут использовать службы TCP и UDP с классами <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> и <xref:System.Net.Sockets.UdpClient>.</span><span class="sxs-lookup"><span data-stu-id="2a2d9-103">Applications can use Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) services with the <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes.</span></span> <span data-ttu-id="2a2d9-104">Эти классы протоколов основаны на классе <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> и управляют различными аспектами передачи данных.</span><span class="sxs-lookup"><span data-stu-id="2a2d9-104">These protocol classes are built on top of the <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> class and take care of the details of transferring data.</span></span>  
  
 <span data-ttu-id="2a2d9-105">Классы протоколов используют синхронные методы класса **Socket** для обеспечения простого доступа к сетевым службам без накладных расходов, связанных с сохранением сведений о состоянии. При этом также не требуется знать особенности настройки сокетов для определенного протокола.</span><span class="sxs-lookup"><span data-stu-id="2a2d9-105">The protocol classes use the synchronous methods of the **Socket** class to provide simple and straightforward access to network services without the overhead of maintaining state information or knowing the details of setting up protocol-specific sockets.</span></span> <span data-ttu-id="2a2d9-106">Для использования асинхронных методов **Socket** можно применять асинхронные методы, предоставляемые классом <xref:System.Net.Sockets.NetworkStream>.</span><span class="sxs-lookup"><span data-stu-id="2a2d9-106">To use asynchronous **Socket** methods, you can use the asynchronous methods supplied by the <xref:System.Net.Sockets.NetworkStream> class.</span></span> <span data-ttu-id="2a2d9-107">Для доступа к возможностям класса **Socket**, которые не предоставляются классами протоколов, необходимо использовать класс **Socket**.</span><span class="sxs-lookup"><span data-stu-id="2a2d9-107">To access features of the **Socket** class not exposed by the protocol classes, you must use the **Socket** class.</span></span>  
  
 <span data-ttu-id="2a2d9-108">**TcpClient** и **TcpListener** представляют сеть с помощью класса **NetworkStream**.</span><span class="sxs-lookup"><span data-stu-id="2a2d9-108">**TcpClient** and **TcpListener** represent the network using the **NetworkStream** class.</span></span> <span data-ttu-id="2a2d9-109">С помощью метода <xref:System.Net.Sockets.TcpClient.GetStream%2A> возвращается сетевой поток, после чего вызываются методы <xref:System.Net.Sockets.NetworkStream.Read%2A> и <xref:System.Net.Sockets.NetworkStream.Write%2A> потока.</span><span class="sxs-lookup"><span data-stu-id="2a2d9-109">You use the <xref:System.Net.Sockets.TcpClient.GetStream%2A> method to return the network stream, and then call the stream's <xref:System.Net.Sockets.NetworkStream.Read%2A> and <xref:System.Net.Sockets.NetworkStream.Write%2A> methods.</span></span> <span data-ttu-id="2a2d9-110">Базовый сокет классов протоколов не принадлежит классу **NetworkStream**, поэтому закрытие этого класса не влияет на сокет.</span><span class="sxs-lookup"><span data-stu-id="2a2d9-110">The **NetworkStream** does not own the protocol classes' underlying socket, so closing it does not affect the socket.</span></span>  
  
 <span data-ttu-id="2a2d9-111">Класс **UdpClient** использует массив байтов для хранения датаграммы UDP.</span><span class="sxs-lookup"><span data-stu-id="2a2d9-111">The **UdpClient** class uses an array of bytes to hold the UDP datagram.</span></span> <span data-ttu-id="2a2d9-112">С помощью метода <xref:System.Net.Sockets.UdpClient.Send%2A> данные отправляются в сеть, а с помощью метода <xref:System.Net.Sockets.UdpClient.Receive%2A> принимается входящая датаграмма.</span><span class="sxs-lookup"><span data-stu-id="2a2d9-112">You use the <xref:System.Net.Sockets.UdpClient.Send%2A> method to send the data to the network and the <xref:System.Net.Sockets.UdpClient.Receive%2A> method to receive an incoming datagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a2d9-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2a2d9-113">See also</span></span>

- [<span data-ttu-id="2a2d9-114">Использование служб TCP</span><span class="sxs-lookup"><span data-stu-id="2a2d9-114">Using TCP Services</span></span>](using-tcp-services.md)
- [<span data-ttu-id="2a2d9-115">Использование служб UDP</span><span class="sxs-lookup"><span data-stu-id="2a2d9-115">Using UDP Services</span></span>](using-udp-services.md)
- [<span data-ttu-id="2a2d9-116">Использование потоков в сети</span><span class="sxs-lookup"><span data-stu-id="2a2d9-116">Using Streams on the Network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="2a2d9-117">Использование асинхронных сокетов сервера</span><span class="sxs-lookup"><span data-stu-id="2a2d9-117">Using an Asynchronous Server Socket</span></span>](using-an-asynchronous-server-socket.md)
- [<span data-ttu-id="2a2d9-118">Использование асинхронных сокетов клиента</span><span class="sxs-lookup"><span data-stu-id="2a2d9-118">Using an Asynchronous Client Socket</span></span>](using-an-asynchronous-client-socket.md)
- [<span data-ttu-id="2a2d9-119">Использование протоколов приложений</span><span class="sxs-lookup"><span data-stu-id="2a2d9-119">Using Application Protocols</span></span>](using-application-protocols.md)
