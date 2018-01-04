---
title: 4812 - DiscoveryMessageWithNullReplyTo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a40e6b7e-c2a6-4186-b1d6-c9560f24a959
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e086c4560515b85d2ea291a8fb71999f13af92eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="4812---discoverymessagewithnullreplyto"></a><span data-ttu-id="2b9a0-102">4812 - DiscoveryMessageWithNullReplyTo</span><span class="sxs-lookup"><span data-stu-id="2b9a0-102">4812 - DiscoveryMessageWithNullReplyTo</span></span>
## <a name="properties"></a><span data-ttu-id="2b9a0-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2b9a0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b9a0-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="2b9a0-104">ID</span></span>|<span data-ttu-id="2b9a0-105">4812</span><span class="sxs-lookup"><span data-stu-id="2b9a0-105">4812</span></span>|  
|<span data-ttu-id="2b9a0-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2b9a0-106">Keywords</span></span>|<span data-ttu-id="2b9a0-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="2b9a0-107">Discovery</span></span>|  
|<span data-ttu-id="2b9a0-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="2b9a0-108">Level</span></span>|<span data-ttu-id="2b9a0-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="2b9a0-109">Warning</span></span>|  
|<span data-ttu-id="2b9a0-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2b9a0-110">Channel</span></span>|<span data-ttu-id="2b9a0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2b9a0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2b9a0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2b9a0-112">Description</span></span>  
 <span data-ttu-id="2b9a0-113">Это событие создается при удалении клиентом DiscoveryClient сообщения запроса обнаружения из-за отсутствия в нем адреса ReplyTo.</span><span class="sxs-lookup"><span data-stu-id="2b9a0-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because it did not have a ReplyTo address.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2b9a0-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2b9a0-114">Message</span></span>  
 <span data-ttu-id="2b9a0-115">Сообщение запроса обнаружения с messageId="%1" удалено, поскольку отсутствует адрес ReplyTo.</span><span class="sxs-lookup"><span data-stu-id="2b9a0-115">A discovery request message with messageId='%1' was dropped because it did not have a ReplyTo address.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2b9a0-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="2b9a0-116">Details</span></span>
