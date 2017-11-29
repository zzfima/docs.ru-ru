---
title: "Примеры кода сокетов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- Socket class, asynchronous server sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- sockets, code examples
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: f3fc7533-6956-42c6-bbc3-73e5a221027d
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ac2363ce7c2affcc0b56f7ce8b9d41180b4c3a1f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="socket-code-examples"></a><span data-ttu-id="8ce1b-102">Примеры кода сокетов</span><span class="sxs-lookup"><span data-stu-id="8ce1b-102">Socket Code Examples</span></span>
<span data-ttu-id="8ce1b-103">В следующем примере кода демонстрируется использование класса <xref:System.Net.Sockets.Socket> в качестве клиента для подключения к удаленным сетевым службам и в качестве сервера для прослушивания подключений удаленных клиентов.</span><span class="sxs-lookup"><span data-stu-id="8ce1b-103">The following code examples demonstrate how to use the <xref:System.Net.Sockets.Socket> class as a client to connect to remote network services and as a server to listen for connections from remote clients.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ce1b-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="8ce1b-104">In This Section</span></span>  
 [<span data-ttu-id="8ce1b-105">Пример синхронного сокета клиента</span><span class="sxs-lookup"><span data-stu-id="8ce1b-105">Synchronous Client Socket Example</span></span>](../../../docs/framework/network-programming/synchronous-client-socket-example.md)  
 <span data-ttu-id="8ce1b-106">Показывает, как реализовать синхронный клиент <xref:System.Net.Sockets.Socket>, который подключается к серверу и отображает возвращаемые сервером данные.</span><span class="sxs-lookup"><span data-stu-id="8ce1b-106">Shows how to implement a synchronous <xref:System.Net.Sockets.Socket> client that connects to a server and displays the data returned from the server.</span></span>  
  
 [<span data-ttu-id="8ce1b-107">Пример синхронного сокета сервера</span><span class="sxs-lookup"><span data-stu-id="8ce1b-107">Synchronous Server Socket Example</span></span>](../../../docs/framework/network-programming/synchronous-server-socket-example.md)  
 <span data-ttu-id="8ce1b-108">Показывает, как реализовать синхронный сервер <xref:System.Net.Sockets.Socket>, который принимает подключения клиента и возвращает обратно полученные от клиента данные.</span><span class="sxs-lookup"><span data-stu-id="8ce1b-108">Shows how to implement a synchronous <xref:System.Net.Sockets.Socket> server that accepts connections from a client and echoes back the data received from the client.</span></span>  
  
 [<span data-ttu-id="8ce1b-109">Примеры асинхронных сокетов клиента</span><span class="sxs-lookup"><span data-stu-id="8ce1b-109">Asynchronous Client Socket Example</span></span>](../../../docs/framework/network-programming/asynchronous-client-socket-example.md)  
 <span data-ttu-id="8ce1b-110">Показывает, как реализовать асинхронный клиент <xref:System.Net.Sockets.Socket>, который подключается к серверу и отображает возвращаемые сервером данные.</span><span class="sxs-lookup"><span data-stu-id="8ce1b-110">Shows how to implement an asynchronous <xref:System.Net.Sockets.Socket> client that connects to a server and displays the data returned from the server.</span></span>  
  
 [<span data-ttu-id="8ce1b-111">Пример асинхронного сокета сервера</span><span class="sxs-lookup"><span data-stu-id="8ce1b-111">Asynchronous Server Socket Example</span></span>](../../../docs/framework/network-programming/asynchronous-server-socket-example.md)  
 <span data-ttu-id="8ce1b-112">Показывает, как реализовать асинхронный сервер <xref:System.Net.Sockets.Socket>, который принимает подключения клиента и возвращает обратно полученные от клиента данные.</span><span class="sxs-lookup"><span data-stu-id="8ce1b-112">Shows how to implement an asynchronous <xref:System.Net.Sockets.Socket> server that accepts connections from a client and echoes back the data received from the client.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8ce1b-113">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="8ce1b-113">Related Sections</span></span>  
 [<span data-ttu-id="8ce1b-114">Сокеты</span><span class="sxs-lookup"><span data-stu-id="8ce1b-114">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)  
 <span data-ttu-id="8ce1b-115">Основные сведения о пространстве имен <xref:System.Net.Sockets> и классе <xref:System.Net.Sockets.Socket>.</span><span class="sxs-lookup"><span data-stu-id="8ce1b-115">Provides basic information about the <xref:System.Net.Sockets> namespace and the <xref:System.Net.Sockets.Socket> class.</span></span>  
  
 [<span data-ttu-id="8ce1b-116">Безопасность в сетевом программировании</span><span class="sxs-lookup"><span data-stu-id="8ce1b-116">Security in Network Programming</span></span>](../../../docs/framework/network-programming/security-in-network-programming.md)  
 <span data-ttu-id="8ce1b-117">Описание использования стандартных методов безопасности и аутентификации в Интернете.</span><span class="sxs-lookup"><span data-stu-id="8ce1b-117">Describes how to use standard Internet security and authentication techniques.</span></span>
