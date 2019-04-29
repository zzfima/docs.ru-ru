---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: 416feb4073b31178b016ae72c9cd85e15c4a68c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774417"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="74de5-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="74de5-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="74de5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="74de5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="74de5-104">ID</span><span class="sxs-lookup"><span data-stu-id="74de5-104">ID</span></span>|<span data-ttu-id="74de5-105">39458</span><span class="sxs-lookup"><span data-stu-id="74de5-105">39458</span></span>|  
|<span data-ttu-id="74de5-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="74de5-106">Keywords</span></span>|<span data-ttu-id="74de5-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="74de5-107">WFTracking</span></span>|  
|<span data-ttu-id="74de5-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="74de5-108">Level</span></span>|<span data-ttu-id="74de5-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="74de5-109">Warning</span></span>|  
|<span data-ttu-id="74de5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="74de5-110">Channel</span></span>|<span data-ttu-id="74de5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="74de5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="74de5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="74de5-112">Description</span></span>  
 <span data-ttu-id="74de5-113">Указывает, что запись отслеживания была усечена.</span><span class="sxs-lookup"><span data-stu-id="74de5-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="74de5-114">Данные переменных, заметок, пользователей удалены.</span><span class="sxs-lookup"><span data-stu-id="74de5-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="74de5-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="74de5-115">Message</span></span>  
 <span data-ttu-id="74de5-116">Усеченная запись отслеживания %1 записана в сеанс трассировки событий Windows с использованием поставщика %2.</span><span class="sxs-lookup"><span data-stu-id="74de5-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="74de5-117">Данные переменных, заметок, пользователей удалены</span><span class="sxs-lookup"><span data-stu-id="74de5-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="74de5-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="74de5-118">Details</span></span>  
  
|<span data-ttu-id="74de5-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="74de5-119">Data Item Name</span></span>|<span data-ttu-id="74de5-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="74de5-120">Data Item Type</span></span>|<span data-ttu-id="74de5-121">Описание</span><span class="sxs-lookup"><span data-stu-id="74de5-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="74de5-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="74de5-122">RecordNumber</span></span>|<span data-ttu-id="74de5-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="74de5-123">xs:string</span></span>|<span data-ttu-id="74de5-124">Номер записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="74de5-124">The tracking record number.</span></span>|  
|<span data-ttu-id="74de5-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="74de5-125">ProviderId</span></span>|<span data-ttu-id="74de5-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="74de5-126">xs:string</span></span>|<span data-ttu-id="74de5-127">Идентификатор поставщика трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="74de5-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="74de5-128">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="74de5-128">AppDomain</span></span>|<span data-ttu-id="74de5-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="74de5-129">xs:string</span></span>|<span data-ttu-id="74de5-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="74de5-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
