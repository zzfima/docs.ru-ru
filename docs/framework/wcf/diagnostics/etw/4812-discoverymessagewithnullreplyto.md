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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dad079e4cd2a781d9a8fe7dea388f44400549a63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="4812---discoverymessagewithnullreplyto"></a><span data-ttu-id="e0a5c-102">4812 - DiscoveryMessageWithNullReplyTo</span><span class="sxs-lookup"><span data-stu-id="e0a5c-102">4812 - DiscoveryMessageWithNullReplyTo</span></span>
## <a name="properties"></a><span data-ttu-id="e0a5c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="e0a5c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0a5c-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="e0a5c-104">ID</span></span>|<span data-ttu-id="e0a5c-105">4812</span><span class="sxs-lookup"><span data-stu-id="e0a5c-105">4812</span></span>|  
|<span data-ttu-id="e0a5c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e0a5c-106">Keywords</span></span>|<span data-ttu-id="e0a5c-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="e0a5c-107">Discovery</span></span>|  
|<span data-ttu-id="e0a5c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="e0a5c-108">Level</span></span>|<span data-ttu-id="e0a5c-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="e0a5c-109">Warning</span></span>|  
|<span data-ttu-id="e0a5c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="e0a5c-110">Channel</span></span>|<span data-ttu-id="e0a5c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e0a5c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e0a5c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e0a5c-112">Description</span></span>  
 <span data-ttu-id="e0a5c-113">Это событие создается при удалении клиентом DiscoveryClient сообщения запроса обнаружения из-за отсутствия в нем адреса ReplyTo.</span><span class="sxs-lookup"><span data-stu-id="e0a5c-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because it did not have a ReplyTo address.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e0a5c-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e0a5c-114">Message</span></span>  
 <span data-ttu-id="e0a5c-115">Сообщение запроса обнаружения с messageId="%1" удалено, поскольку отсутствует адрес ReplyTo.</span><span class="sxs-lookup"><span data-stu-id="e0a5c-115">A discovery request message with messageId='%1' was dropped because it did not have a ReplyTo address.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e0a5c-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e0a5c-116">Details</span></span>
