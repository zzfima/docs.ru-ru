---
title: 4811 - DiscoveryMessageWithNullRelatesTo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dab901e8-a2b3-41c1-a76b-bcd8b3c7c29a
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 79e0b1e0a0d155cd640c567059d0d505117d208b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="4811---discoverymessagewithnullrelatesto"></a><span data-ttu-id="31e48-102">4811 - DiscoveryMessageWithNullRelatesTo</span><span class="sxs-lookup"><span data-stu-id="31e48-102">4811 - DiscoveryMessageWithNullRelatesTo</span></span>
## <a name="properties"></a><span data-ttu-id="31e48-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="31e48-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31e48-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="31e48-104">ID</span></span>|<span data-ttu-id="31e48-105">4811</span><span class="sxs-lookup"><span data-stu-id="31e48-105">4811</span></span>|  
|<span data-ttu-id="31e48-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="31e48-106">Keywords</span></span>|<span data-ttu-id="31e48-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="31e48-107">Discovery</span></span>|  
|<span data-ttu-id="31e48-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="31e48-108">Level</span></span>|<span data-ttu-id="31e48-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="31e48-109">Warning</span></span>|  
|<span data-ttu-id="31e48-110">Канал</span><span class="sxs-lookup"><span data-stu-id="31e48-110">Channel</span></span>|<span data-ttu-id="31e48-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="31e48-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="31e48-112">Описание</span><span class="sxs-lookup"><span data-stu-id="31e48-112">Description</span></span>  
 <span data-ttu-id="31e48-113">Это событие создается при удалении сообщения обнаружения объектом DiscoveryClient из-за отсутствия в заголовке сообщения обязательного свойства RelatesTo.</span><span class="sxs-lookup"><span data-stu-id="31e48-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because the message header did not contain the required RelatesTo property.</span></span>  
  
## <a name="message"></a><span data-ttu-id="31e48-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="31e48-114">Message</span></span>  
 <span data-ttu-id="31e48-115">Сообщение %1 с messageId="%2" удалено клиентом DiscoveryClient, поскольку заголовок сообщения не содержит обязательного свойства RelatesTo.</span><span class="sxs-lookup"><span data-stu-id="31e48-115">A %1 message with messageId='%2' was dropped by the DiscoveryClient because the message header did not contain the required RelatesTo property.</span></span>  
  
## <a name="details"></a><span data-ttu-id="31e48-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="31e48-116">Details</span></span>
