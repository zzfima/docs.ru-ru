---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e785e40afcb91620940f952022eda4c4b799f4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="567d4-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="567d4-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="567d4-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="567d4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="567d4-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="567d4-104">ID</span></span>|<span data-ttu-id="567d4-105">3551</span><span class="sxs-lookup"><span data-stu-id="567d4-105">3551</span></span>|  
|<span data-ttu-id="567d4-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="567d4-106">Keywords</span></span>|<span data-ttu-id="567d4-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="567d4-107">WFServices</span></span>|  
|<span data-ttu-id="567d4-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="567d4-108">Level</span></span>|<span data-ttu-id="567d4-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="567d4-109">Information</span></span>|  
|<span data-ttu-id="567d4-110">Канал</span><span class="sxs-lookup"><span data-stu-id="567d4-110">Channel</span></span>|<span data-ttu-id="567d4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="567d4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="567d4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="567d4-112">Description</span></span>  
 <span data-ttu-id="567d4-113">Указывает на сбой возобновления закладки.</span><span class="sxs-lookup"><span data-stu-id="567d4-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="567d4-114">Следующая попытка выполнить операцию получения через буфер будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="567d4-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="567d4-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="567d4-115">Message</span></span>  
 <span data-ttu-id="567d4-116">Операция «%2» в экземпляре службы «%1» не может быть выполнена в данный момент.</span><span class="sxs-lookup"><span data-stu-id="567d4-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="567d4-117">Следующая попытка будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="567d4-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="567d4-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="567d4-118">Details</span></span>  
  
|<span data-ttu-id="567d4-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="567d4-119">Data Item Name</span></span>|<span data-ttu-id="567d4-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="567d4-120">Data Item Type</span></span>|<span data-ttu-id="567d4-121">Описание</span><span class="sxs-lookup"><span data-stu-id="567d4-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="567d4-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="567d4-122">OperationName</span></span>|<span data-ttu-id="567d4-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="567d4-123">xs:string</span></span>|<span data-ttu-id="567d4-124">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="567d4-124">The name of the operation.</span></span>|  
|<span data-ttu-id="567d4-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="567d4-125">ServiceInstanceId</span></span>|<span data-ttu-id="567d4-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="567d4-126">xs:string</span></span>|<span data-ttu-id="567d4-127">Идентификатор экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="567d4-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="567d4-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="567d4-128">AppDomain</span></span>|<span data-ttu-id="567d4-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="567d4-129">xs:string</span></span>|<span data-ttu-id="567d4-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="567d4-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
