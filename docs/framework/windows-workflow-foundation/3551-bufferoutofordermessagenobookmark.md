---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 89643edde5856688c762b0cf0d188bd4e7ba8a24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="67f3c-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="67f3c-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="67f3c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="67f3c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67f3c-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="67f3c-104">ID</span></span>|<span data-ttu-id="67f3c-105">3551</span><span class="sxs-lookup"><span data-stu-id="67f3c-105">3551</span></span>|  
|<span data-ttu-id="67f3c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="67f3c-106">Keywords</span></span>|<span data-ttu-id="67f3c-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="67f3c-107">WFServices</span></span>|  
|<span data-ttu-id="67f3c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="67f3c-108">Level</span></span>|<span data-ttu-id="67f3c-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="67f3c-109">Information</span></span>|  
|<span data-ttu-id="67f3c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="67f3c-110">Channel</span></span>|<span data-ttu-id="67f3c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="67f3c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="67f3c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="67f3c-112">Description</span></span>  
 <span data-ttu-id="67f3c-113">Указывает на сбой возобновления закладки.</span><span class="sxs-lookup"><span data-stu-id="67f3c-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="67f3c-114">Следующая попытка выполнить операцию получения через буфер будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="67f3c-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="67f3c-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="67f3c-115">Message</span></span>  
 <span data-ttu-id="67f3c-116">Операция «%2» в экземпляре службы «%1» не может быть выполнена в данный момент.</span><span class="sxs-lookup"><span data-stu-id="67f3c-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="67f3c-117">Следующая попытка будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="67f3c-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="67f3c-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="67f3c-118">Details</span></span>  
  
|<span data-ttu-id="67f3c-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="67f3c-119">Data Item Name</span></span>|<span data-ttu-id="67f3c-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="67f3c-120">Data Item Type</span></span>|<span data-ttu-id="67f3c-121">Описание</span><span class="sxs-lookup"><span data-stu-id="67f3c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="67f3c-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="67f3c-122">OperationName</span></span>|<span data-ttu-id="67f3c-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="67f3c-123">xs:string</span></span>|<span data-ttu-id="67f3c-124">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="67f3c-124">The name of the operation.</span></span>|  
|<span data-ttu-id="67f3c-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="67f3c-125">ServiceInstanceId</span></span>|<span data-ttu-id="67f3c-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="67f3c-126">xs:string</span></span>|<span data-ttu-id="67f3c-127">Идентификатор экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="67f3c-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="67f3c-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="67f3c-128">AppDomain</span></span>|<span data-ttu-id="67f3c-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="67f3c-129">xs:string</span></span>|<span data-ttu-id="67f3c-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="67f3c-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
