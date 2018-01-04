---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 435a6a4390d52555d353a25ac119934087cf9c87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="6c47f-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="6c47f-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="6c47f-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="6c47f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6c47f-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="6c47f-104">ID</span></span>|<span data-ttu-id="6c47f-105">3550</span><span class="sxs-lookup"><span data-stu-id="6c47f-105">3550</span></span>|  
|<span data-ttu-id="6c47f-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6c47f-106">Keywords</span></span>|<span data-ttu-id="6c47f-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="6c47f-107">WFServices</span></span>|  
|<span data-ttu-id="6c47f-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="6c47f-108">Level</span></span>|<span data-ttu-id="6c47f-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="6c47f-109">Information</span></span>|  
|<span data-ttu-id="6c47f-110">Канал</span><span class="sxs-lookup"><span data-stu-id="6c47f-110">Channel</span></span>|<span data-ttu-id="6c47f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="6c47f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6c47f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6c47f-112">Description</span></span>  
 <span data-ttu-id="6c47f-113">Указывает, что получение через буфер не удалось.</span><span class="sxs-lookup"><span data-stu-id="6c47f-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="6c47f-114">Следующая попытка выполнить операцию будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="6c47f-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6c47f-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="6c47f-115">Message</span></span>  
 <span data-ttu-id="6c47f-116">Операция «%1» сейчас не может быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="6c47f-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="6c47f-117">Следующая попытка будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="6c47f-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6c47f-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="6c47f-118">Details</span></span>  
  
|<span data-ttu-id="6c47f-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="6c47f-119">Data Item Name</span></span>|<span data-ttu-id="6c47f-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="6c47f-120">Data Item Type</span></span>|<span data-ttu-id="6c47f-121">Описание</span><span class="sxs-lookup"><span data-stu-id="6c47f-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6c47f-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="6c47f-122">OperationName</span></span>|<span data-ttu-id="6c47f-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="6c47f-123">xs:string</span></span>|<span data-ttu-id="6c47f-124">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="6c47f-124">The name of the operation.</span></span>|  
|<span data-ttu-id="6c47f-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6c47f-125">AppDomain</span></span>|<span data-ttu-id="6c47f-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="6c47f-126">xs:string</span></span>|<span data-ttu-id="6c47f-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6c47f-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
