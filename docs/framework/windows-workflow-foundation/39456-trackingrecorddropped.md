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
ms.workload: dotnet
ms.openlocfilehash: 592d7c0a3725dcb50f7911a198c9dc9b7199a0a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="2c962-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="2c962-102">39456 - TrackingRecordDropped</span></span>
## <a name="properties"></a><span data-ttu-id="2c962-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2c962-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2c962-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="2c962-104">ID</span></span>|<span data-ttu-id="2c962-105">39456</span><span class="sxs-lookup"><span data-stu-id="2c962-105">39456</span></span>|  
|<span data-ttu-id="2c962-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2c962-106">Keywords</span></span>|<span data-ttu-id="2c962-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="2c962-107">WFTracking</span></span>|  
|<span data-ttu-id="2c962-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="2c962-108">Level</span></span>|<span data-ttu-id="2c962-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="2c962-109">Warning</span></span>|  
|<span data-ttu-id="2c962-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2c962-110">Channel</span></span>|<span data-ttu-id="2c962-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2c962-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2c962-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2c962-112">Description</span></span>  
 <span data-ttu-id="2c962-113">Указывает, что запись отслеживания была удалена, поскольку ее размер превышает максимум, поддерживаемый поставщиком сеанса трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="2c962-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2c962-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2c962-114">Message</span></span>  
 <span data-ttu-id="2c962-115">Размер записи отслеживания %1 превышает максимально допустимое значение, разрешенное в сеансе трассировки событий Windows для поставщика %2</span><span class="sxs-lookup"><span data-stu-id="2c962-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="2c962-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="2c962-116">Details</span></span>  
  
|<span data-ttu-id="2c962-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="2c962-117">Data Item Name</span></span>|<span data-ttu-id="2c962-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="2c962-118">Data Item Type</span></span>|<span data-ttu-id="2c962-119">Описание</span><span class="sxs-lookup"><span data-stu-id="2c962-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2c962-120">Исключение</span><span class="sxs-lookup"><span data-stu-id="2c962-120">Exception</span></span>|<span data-ttu-id="2c962-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2c962-121">xs:string</span></span>|<span data-ttu-id="2c962-122">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="2c962-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="2c962-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2c962-123">AppDomain</span></span>|<span data-ttu-id="2c962-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2c962-124">xs:string</span></span>|<span data-ttu-id="2c962-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2c962-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
