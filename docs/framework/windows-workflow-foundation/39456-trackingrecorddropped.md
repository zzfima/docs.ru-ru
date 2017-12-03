---
title: 39456 - TrackingRecordDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de056ffcdfeb3ea5dee9eaca213fe96ee991d067
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="48bd2-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="48bd2-102">39456 - TrackingRecordDropped</span></span>
## <a name="properties"></a><span data-ttu-id="48bd2-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="48bd2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48bd2-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="48bd2-104">ID</span></span>|<span data-ttu-id="48bd2-105">39456</span><span class="sxs-lookup"><span data-stu-id="48bd2-105">39456</span></span>|  
|<span data-ttu-id="48bd2-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="48bd2-106">Keywords</span></span>|<span data-ttu-id="48bd2-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="48bd2-107">WFTracking</span></span>|  
|<span data-ttu-id="48bd2-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="48bd2-108">Level</span></span>|<span data-ttu-id="48bd2-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="48bd2-109">Warning</span></span>|  
|<span data-ttu-id="48bd2-110">Канал</span><span class="sxs-lookup"><span data-stu-id="48bd2-110">Channel</span></span>|<span data-ttu-id="48bd2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="48bd2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="48bd2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="48bd2-112">Description</span></span>  
 <span data-ttu-id="48bd2-113">Указывает, что запись отслеживания была удалена, поскольку ее размер превышает максимум, поддерживаемый поставщиком сеанса трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="48bd2-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="48bd2-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="48bd2-114">Message</span></span>  
 <span data-ttu-id="48bd2-115">Размер записи отслеживания %1 превышает максимально допустимое значение, разрешенное в сеансе трассировки событий Windows для поставщика %2</span><span class="sxs-lookup"><span data-stu-id="48bd2-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="48bd2-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="48bd2-116">Details</span></span>  
  
|<span data-ttu-id="48bd2-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="48bd2-117">Data Item Name</span></span>|<span data-ttu-id="48bd2-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="48bd2-118">Data Item Type</span></span>|<span data-ttu-id="48bd2-119">Описание</span><span class="sxs-lookup"><span data-stu-id="48bd2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="48bd2-120">Исключение</span><span class="sxs-lookup"><span data-stu-id="48bd2-120">Exception</span></span>|<span data-ttu-id="48bd2-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="48bd2-121">xs:string</span></span>|<span data-ttu-id="48bd2-122">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="48bd2-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="48bd2-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="48bd2-123">AppDomain</span></span>|<span data-ttu-id="48bd2-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="48bd2-124">xs:string</span></span>|<span data-ttu-id="48bd2-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="48bd2-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
