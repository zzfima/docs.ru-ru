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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1925e11e2b572f66f5c9da9f48b5110ff3db6e31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="4810---discoverymessagewithnullmessagesequence"></a><span data-ttu-id="34afe-102">4810 - DiscoveryMessageWithNullMessageSequence</span><span class="sxs-lookup"><span data-stu-id="34afe-102">4810 - DiscoveryMessageWithNullMessageSequence</span></span>
## <a name="properties"></a><span data-ttu-id="34afe-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="34afe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34afe-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="34afe-104">ID</span></span>|<span data-ttu-id="34afe-105">4810</span><span class="sxs-lookup"><span data-stu-id="34afe-105">4810</span></span>|  
|<span data-ttu-id="34afe-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="34afe-106">Keywords</span></span>|<span data-ttu-id="34afe-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="34afe-107">Discovery</span></span>|  
|<span data-ttu-id="34afe-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="34afe-108">Level</span></span>|<span data-ttu-id="34afe-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="34afe-109">Warning</span></span>|  
|<span data-ttu-id="34afe-110">Канал</span><span class="sxs-lookup"><span data-stu-id="34afe-110">Channel</span></span>|<span data-ttu-id="34afe-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="34afe-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="34afe-112">Описание</span><span class="sxs-lookup"><span data-stu-id="34afe-112">Description</span></span>  
 <span data-ttu-id="34afe-113">Это событие создается при удалении клиентом DiscoveryClient сообщения запроса обнаружения из-за отсутствия в нем свойства DiscoveryMessageSequence.</span><span class="sxs-lookup"><span data-stu-id="34afe-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because it did not have the DiscoveryMessageSequence property.</span></span>  
  
## <a name="message"></a><span data-ttu-id="34afe-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="34afe-114">Message</span></span>  
 <span data-ttu-id="34afe-115">Сообщение %1 с messageId="%2" удалено клиентом DiscoveryClient, поскольку в нем отсутствует свойство DiscoveryMessageSequence.</span><span class="sxs-lookup"><span data-stu-id="34afe-115">A %1 message with messageId='%2' was dropped by the DiscoveryClient because it did not have the DiscoveryMessageSequence property.</span></span>  
  
## <a name="details"></a><span data-ttu-id="34afe-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="34afe-116">Details</span></span>
