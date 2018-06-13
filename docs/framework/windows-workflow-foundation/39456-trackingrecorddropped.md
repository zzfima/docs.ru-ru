---
title: 39456 - TrackingRecordDropped
ms.date: 03/30/2017
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
ms.openlocfilehash: f117c7759bab1759a7d614db275de88f8b37c331
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510709"
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="4b82e-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="4b82e-102">39456 - TrackingRecordDropped</span></span>
## <a name="properties"></a><span data-ttu-id="4b82e-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="4b82e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b82e-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="4b82e-104">ID</span></span>|<span data-ttu-id="4b82e-105">39456</span><span class="sxs-lookup"><span data-stu-id="4b82e-105">39456</span></span>|  
|<span data-ttu-id="4b82e-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="4b82e-106">Keywords</span></span>|<span data-ttu-id="4b82e-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="4b82e-107">WFTracking</span></span>|  
|<span data-ttu-id="4b82e-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="4b82e-108">Level</span></span>|<span data-ttu-id="4b82e-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="4b82e-109">Warning</span></span>|  
|<span data-ttu-id="4b82e-110">Канал</span><span class="sxs-lookup"><span data-stu-id="4b82e-110">Channel</span></span>|<span data-ttu-id="4b82e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4b82e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4b82e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4b82e-112">Description</span></span>  
 <span data-ttu-id="4b82e-113">Указывает, что запись отслеживания была удалена, поскольку ее размер превышает максимум, поддерживаемый поставщиком сеанса трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="4b82e-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4b82e-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="4b82e-114">Message</span></span>  
 <span data-ttu-id="4b82e-115">Размер записи отслеживания %1 превышает максимально допустимое значение, разрешенное в сеансе трассировки событий Windows для поставщика %2</span><span class="sxs-lookup"><span data-stu-id="4b82e-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="4b82e-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="4b82e-116">Details</span></span>  
  
|<span data-ttu-id="4b82e-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="4b82e-117">Data Item Name</span></span>|<span data-ttu-id="4b82e-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="4b82e-118">Data Item Type</span></span>|<span data-ttu-id="4b82e-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4b82e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4b82e-120">Исключение</span><span class="sxs-lookup"><span data-stu-id="4b82e-120">Exception</span></span>|<span data-ttu-id="4b82e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b82e-121">xs:string</span></span>|<span data-ttu-id="4b82e-122">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="4b82e-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="4b82e-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4b82e-123">AppDomain</span></span>|<span data-ttu-id="4b82e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b82e-124">xs:string</span></span>|<span data-ttu-id="4b82e-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4b82e-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
