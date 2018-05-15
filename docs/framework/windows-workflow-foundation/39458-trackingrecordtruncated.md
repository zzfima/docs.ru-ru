---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: 416feb4073b31178b016ae72c9cd85e15c4a68c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="abddf-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="abddf-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="abddf-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="abddf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="abddf-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="abddf-104">ID</span></span>|<span data-ttu-id="abddf-105">39458</span><span class="sxs-lookup"><span data-stu-id="abddf-105">39458</span></span>|  
|<span data-ttu-id="abddf-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="abddf-106">Keywords</span></span>|<span data-ttu-id="abddf-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="abddf-107">WFTracking</span></span>|  
|<span data-ttu-id="abddf-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="abddf-108">Level</span></span>|<span data-ttu-id="abddf-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="abddf-109">Warning</span></span>|  
|<span data-ttu-id="abddf-110">Канал</span><span class="sxs-lookup"><span data-stu-id="abddf-110">Channel</span></span>|<span data-ttu-id="abddf-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="abddf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="abddf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="abddf-112">Description</span></span>  
 <span data-ttu-id="abddf-113">Указывает, что запись отслеживания была усечена.</span><span class="sxs-lookup"><span data-stu-id="abddf-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="abddf-114">Данные переменных, заметок, пользователей удалены.</span><span class="sxs-lookup"><span data-stu-id="abddf-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="abddf-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="abddf-115">Message</span></span>  
 <span data-ttu-id="abddf-116">Усеченная запись отслеживания %1 записана в сеанс трассировки событий Windows с использованием поставщика %2.</span><span class="sxs-lookup"><span data-stu-id="abddf-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="abddf-117">Данные переменных, заметок, пользователей удалены</span><span class="sxs-lookup"><span data-stu-id="abddf-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="abddf-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="abddf-118">Details</span></span>  
  
|<span data-ttu-id="abddf-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="abddf-119">Data Item Name</span></span>|<span data-ttu-id="abddf-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="abddf-120">Data Item Type</span></span>|<span data-ttu-id="abddf-121">Описание</span><span class="sxs-lookup"><span data-stu-id="abddf-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="abddf-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="abddf-122">RecordNumber</span></span>|<span data-ttu-id="abddf-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="abddf-123">xs:string</span></span>|<span data-ttu-id="abddf-124">Номер записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="abddf-124">The tracking record number.</span></span>|  
|<span data-ttu-id="abddf-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="abddf-125">ProviderId</span></span>|<span data-ttu-id="abddf-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="abddf-126">xs:string</span></span>|<span data-ttu-id="abddf-127">Идентификатор поставщика трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="abddf-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="abddf-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="abddf-128">AppDomain</span></span>|<span data-ttu-id="abddf-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="abddf-129">xs:string</span></span>|<span data-ttu-id="abddf-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="abddf-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
