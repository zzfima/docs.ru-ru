---
title: 4810 - DiscoveryMessageWithNullMessageSequence
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa70573e-8a76-486a-9616-ccca8c7008b6
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 55e2c1121ec97f49021845c5237b2e3d63a78083
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="4810---discoverymessagewithnullmessagesequence"></a><span data-ttu-id="a72b6-102">4810 - DiscoveryMessageWithNullMessageSequence</span><span class="sxs-lookup"><span data-stu-id="a72b6-102">4810 - DiscoveryMessageWithNullMessageSequence</span></span>
## <a name="properties"></a><span data-ttu-id="a72b6-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a72b6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a72b6-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="a72b6-104">ID</span></span>|<span data-ttu-id="a72b6-105">4810</span><span class="sxs-lookup"><span data-stu-id="a72b6-105">4810</span></span>|  
|<span data-ttu-id="a72b6-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a72b6-106">Keywords</span></span>|<span data-ttu-id="a72b6-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="a72b6-107">Discovery</span></span>|  
|<span data-ttu-id="a72b6-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="a72b6-108">Level</span></span>|<span data-ttu-id="a72b6-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="a72b6-109">Warning</span></span>|  
|<span data-ttu-id="a72b6-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a72b6-110">Channel</span></span>|<span data-ttu-id="a72b6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a72b6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a72b6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a72b6-112">Description</span></span>  
 <span data-ttu-id="a72b6-113">Это событие создается при удалении клиентом DiscoveryClient сообщения запроса обнаружения из-за отсутствия в нем свойства DiscoveryMessageSequence.</span><span class="sxs-lookup"><span data-stu-id="a72b6-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because it did not have the DiscoveryMessageSequence property.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a72b6-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a72b6-114">Message</span></span>  
 <span data-ttu-id="a72b6-115">Сообщение %1 с messageId="%2" удалено клиентом DiscoveryClient, поскольку в нем отсутствует свойство DiscoveryMessageSequence.</span><span class="sxs-lookup"><span data-stu-id="a72b6-115">A %1 message with messageId='%2' was dropped by the DiscoveryClient because it did not have the DiscoveryMessageSequence property.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a72b6-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="a72b6-116">Details</span></span>
