---
title: "Добавление подключенного и отключенного состояния"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05e5f51d-81b6-4c17-b364-9dda447a5fce
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d5b6c858b5aa5918498ba8fccee41f7392ac32e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="adding-online-and-offline-status"></a><span data-ttu-id="b1a7f-102">Добавление подключенного и отключенного состояния</span><span class="sxs-lookup"><span data-stu-id="b1a7f-102">Adding Online and Offline Status</span></span>
<span data-ttu-id="b1a7f-103">Во многих случаях для приложения важно контролировать конкретные сведения о состоянии подключения по одноранговому каналу.</span><span class="sxs-lookup"><span data-stu-id="b1a7f-103">In many cases, it is important for an application to monitor specific details about the status of a Peer Channel connection.</span></span> <span data-ttu-id="b1a7f-104">Эти сведения можно получить, вызвав метод `GetProperty` в реализации интерфейса <xref:System.ServiceModel.IOnlineStatus>.</span><span class="sxs-lookup"><span data-stu-id="b1a7f-104">You can obtain this information by calling the `GetProperty` method on an implementation of the <xref:System.ServiceModel.IOnlineStatus> interface.</span></span> <span data-ttu-id="b1a7f-105">Объект с реализацией этого интерфейса может контролировать состояние подключения или регистрировать обработчики событий, например `OnOnline` и `OnOffline`, и немедленно реагировать при возникновении изменений в состоянии подключения к сети.</span><span class="sxs-lookup"><span data-stu-id="b1a7f-105">An object with an implementation of this interface can monitor connection status or register for event handlers, such as `OnOnline` and `OnOffline`, and react immediately as changes to online status occur.</span></span>  
  
 <span data-ttu-id="b1a7f-106">В инфраструктуре одноранговых каналов клиент считается подключенным к сети, если он подключен по крайней мере к одному одноранговому узлу. В противном случае клиент считается автономным.</span><span class="sxs-lookup"><span data-stu-id="b1a7f-106">In the Peer Channel infrastructure, a client is considered to be online if it is connected to at least one other peer and offline otherwise.</span></span> <span data-ttu-id="b1a7f-107">Это может быть особенно полезно как при отладке разрабатываемых приложений, так и при отображении подробных сведений для конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="b1a7f-107">This can be particularly useful in both debugging a developing applications or displaying detailed information to the end user.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1a7f-108">Перед отправкой любых сообщений обработчик событий подключения к сети должен убедиться, что узел открыт.</span><span class="sxs-lookup"><span data-stu-id="b1a7f-108">An online event handler should first ensure that the node is open before sending any messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1a7f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b1a7f-109">See Also</span></span>  
 [<span data-ttu-id="b1a7f-110">Создание приложения одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="b1a7f-110">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
