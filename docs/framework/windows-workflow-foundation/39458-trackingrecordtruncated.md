---
title: 39458 - TrackingRecordTruncated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d2bc07cff75fce7ddb50da9f54d161d7f235cab
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="1c725-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="1c725-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="1c725-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="1c725-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1c725-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="1c725-104">ID</span></span>|<span data-ttu-id="1c725-105">39458</span><span class="sxs-lookup"><span data-stu-id="1c725-105">39458</span></span>|  
|<span data-ttu-id="1c725-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1c725-106">Keywords</span></span>|<span data-ttu-id="1c725-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="1c725-107">WFTracking</span></span>|  
|<span data-ttu-id="1c725-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="1c725-108">Level</span></span>|<span data-ttu-id="1c725-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="1c725-109">Warning</span></span>|  
|<span data-ttu-id="1c725-110">Канал</span><span class="sxs-lookup"><span data-stu-id="1c725-110">Channel</span></span>|<span data-ttu-id="1c725-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1c725-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1c725-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1c725-112">Description</span></span>  
 <span data-ttu-id="1c725-113">Указывает, что запись отслеживания была усечена.</span><span class="sxs-lookup"><span data-stu-id="1c725-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="1c725-114">Данные переменных, заметок, пользователей удалены.</span><span class="sxs-lookup"><span data-stu-id="1c725-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1c725-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="1c725-115">Message</span></span>  
 <span data-ttu-id="1c725-116">Усеченная запись отслеживания %1 записана в сеанс трассировки событий Windows с использованием поставщика %2.</span><span class="sxs-lookup"><span data-stu-id="1c725-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="1c725-117">Данные переменных, заметок, пользователей удалены</span><span class="sxs-lookup"><span data-stu-id="1c725-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="1c725-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="1c725-118">Details</span></span>  
  
|<span data-ttu-id="1c725-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="1c725-119">Data Item Name</span></span>|<span data-ttu-id="1c725-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="1c725-120">Data Item Type</span></span>|<span data-ttu-id="1c725-121">Описание</span><span class="sxs-lookup"><span data-stu-id="1c725-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1c725-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="1c725-122">RecordNumber</span></span>|<span data-ttu-id="1c725-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c725-123">xs:string</span></span>|<span data-ttu-id="1c725-124">Номер записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="1c725-124">The tracking record number.</span></span>|  
|<span data-ttu-id="1c725-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="1c725-125">ProviderId</span></span>|<span data-ttu-id="1c725-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c725-126">xs:string</span></span>|<span data-ttu-id="1c725-127">Идентификатор поставщика трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="1c725-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="1c725-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1c725-128">AppDomain</span></span>|<span data-ttu-id="1c725-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="1c725-129">xs:string</span></span>|<span data-ttu-id="1c725-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1c725-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
