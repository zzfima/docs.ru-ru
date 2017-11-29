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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ce8b2cd52523d8a2efc94214479ca3c41d2dec4b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="a8bb5-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="a8bb5-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="a8bb5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a8bb5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a8bb5-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="a8bb5-104">ID</span></span>|<span data-ttu-id="a8bb5-105">3550</span><span class="sxs-lookup"><span data-stu-id="a8bb5-105">3550</span></span>|  
|<span data-ttu-id="a8bb5-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a8bb5-106">Keywords</span></span>|<span data-ttu-id="a8bb5-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="a8bb5-107">WFServices</span></span>|  
|<span data-ttu-id="a8bb5-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="a8bb5-108">Level</span></span>|<span data-ttu-id="a8bb5-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="a8bb5-109">Information</span></span>|  
|<span data-ttu-id="a8bb5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a8bb5-110">Channel</span></span>|<span data-ttu-id="a8bb5-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a8bb5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a8bb5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a8bb5-112">Description</span></span>  
 <span data-ttu-id="a8bb5-113">Указывает, что получение через буфер не удалось.</span><span class="sxs-lookup"><span data-stu-id="a8bb5-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="a8bb5-114">Следующая попытка выполнить операцию будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="a8bb5-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a8bb5-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a8bb5-115">Message</span></span>  
 <span data-ttu-id="a8bb5-116">Операция «%1» сейчас не может быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="a8bb5-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="a8bb5-117">Следующая попытка будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="a8bb5-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a8bb5-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="a8bb5-118">Details</span></span>  
  
|<span data-ttu-id="a8bb5-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="a8bb5-119">Data Item Name</span></span>|<span data-ttu-id="a8bb5-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="a8bb5-120">Data Item Type</span></span>|<span data-ttu-id="a8bb5-121">Описание</span><span class="sxs-lookup"><span data-stu-id="a8bb5-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a8bb5-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="a8bb5-122">OperationName</span></span>|<span data-ttu-id="a8bb5-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="a8bb5-123">xs:string</span></span>|<span data-ttu-id="a8bb5-124">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="a8bb5-124">The name of the operation.</span></span>|  
|<span data-ttu-id="a8bb5-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a8bb5-125">AppDomain</span></span>|<span data-ttu-id="a8bb5-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="a8bb5-126">xs:string</span></span>|<span data-ttu-id="a8bb5-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a8bb5-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
