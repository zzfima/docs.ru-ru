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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1a9f4cf65febd955e69d81f8dbb8f97aaa24e68c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="adding-online-and-offline-status"></a><span data-ttu-id="3b298-102">Добавление подключенного и отключенного состояния</span><span class="sxs-lookup"><span data-stu-id="3b298-102">Adding Online and Offline Status</span></span>
<span data-ttu-id="3b298-103">Во многих случаях для приложения важно контролировать конкретные сведения о состоянии подключения по одноранговому каналу.</span><span class="sxs-lookup"><span data-stu-id="3b298-103">In many cases, it is important for an application to monitor specific details about the status of a Peer Channel connection.</span></span> <span data-ttu-id="3b298-104">Эти сведения можно получить, вызвав метод `GetProperty` в реализации интерфейса <xref:System.ServiceModel.IOnlineStatus>.</span><span class="sxs-lookup"><span data-stu-id="3b298-104">You can obtain this information by calling the `GetProperty` method on an implementation of the <xref:System.ServiceModel.IOnlineStatus> interface.</span></span> <span data-ttu-id="3b298-105">Объект с реализацией этого интерфейса может контролировать состояние подключения или регистрировать обработчики событий, например `OnOnline` и `OnOffline`, и немедленно реагировать при возникновении изменений в состоянии подключения к сети.</span><span class="sxs-lookup"><span data-stu-id="3b298-105">An object with an implementation of this interface can monitor connection status or register for event handlers, such as `OnOnline` and `OnOffline`, and react immediately as changes to online status occur.</span></span>  
  
 <span data-ttu-id="3b298-106">В инфраструктуре одноранговых каналов клиент считается подключенным к сети, если он подключен по крайней мере к одному одноранговому узлу. В противном случае клиент считается автономным.</span><span class="sxs-lookup"><span data-stu-id="3b298-106">In the Peer Channel infrastructure, a client is considered to be online if it is connected to at least one other peer and offline otherwise.</span></span> <span data-ttu-id="3b298-107">Это может быть особенно полезно как при отладке разрабатываемых приложений, так и при отображении подробных сведений для конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="3b298-107">This can be particularly useful in both debugging a developing applications or displaying detailed information to the end user.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b298-108">Перед отправкой любых сообщений обработчик событий подключения к сети должен убедиться, что узел открыт.</span><span class="sxs-lookup"><span data-stu-id="3b298-108">An online event handler should first ensure that the node is open before sending any messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b298-109">См. также</span><span class="sxs-lookup"><span data-stu-id="3b298-109">See Also</span></span>  
 [<span data-ttu-id="3b298-110">Создание приложения одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="3b298-110">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
