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
ms.openlocfilehash: eabc6a6915560d8c49e695d5d681f1544689cb07
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="53e06-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="53e06-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="53e06-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="53e06-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53e06-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="53e06-104">ID</span></span>|<span data-ttu-id="53e06-105">3550</span><span class="sxs-lookup"><span data-stu-id="53e06-105">3550</span></span>|  
|<span data-ttu-id="53e06-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="53e06-106">Keywords</span></span>|<span data-ttu-id="53e06-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="53e06-107">WFServices</span></span>|  
|<span data-ttu-id="53e06-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="53e06-108">Level</span></span>|<span data-ttu-id="53e06-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="53e06-109">Information</span></span>|  
|<span data-ttu-id="53e06-110">Канал</span><span class="sxs-lookup"><span data-stu-id="53e06-110">Channel</span></span>|<span data-ttu-id="53e06-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="53e06-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="53e06-112">Описание</span><span class="sxs-lookup"><span data-stu-id="53e06-112">Description</span></span>  
 <span data-ttu-id="53e06-113">Указывает, что получение через буфер не удалось.</span><span class="sxs-lookup"><span data-stu-id="53e06-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="53e06-114">Следующая попытка выполнить операцию будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="53e06-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="53e06-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="53e06-115">Message</span></span>  
 <span data-ttu-id="53e06-116">Операция «%1» сейчас не может быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="53e06-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="53e06-117">Следующая попытка будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="53e06-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="53e06-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="53e06-118">Details</span></span>  
  
|<span data-ttu-id="53e06-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="53e06-119">Data Item Name</span></span>|<span data-ttu-id="53e06-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="53e06-120">Data Item Type</span></span>|<span data-ttu-id="53e06-121">Описание</span><span class="sxs-lookup"><span data-stu-id="53e06-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="53e06-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="53e06-122">OperationName</span></span>|<span data-ttu-id="53e06-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="53e06-123">xs:string</span></span>|<span data-ttu-id="53e06-124">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="53e06-124">The name of the operation.</span></span>|  
|<span data-ttu-id="53e06-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="53e06-125">AppDomain</span></span>|<span data-ttu-id="53e06-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="53e06-126">xs:string</span></span>|<span data-ttu-id="53e06-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="53e06-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
