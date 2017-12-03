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
ms.openlocfilehash: 6dc505a4e0e79b37f9adff41b80dcba55215576f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="44487-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="44487-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="44487-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="44487-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44487-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="44487-104">ID</span></span>|<span data-ttu-id="44487-105">3551</span><span class="sxs-lookup"><span data-stu-id="44487-105">3551</span></span>|  
|<span data-ttu-id="44487-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="44487-106">Keywords</span></span>|<span data-ttu-id="44487-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="44487-107">WFServices</span></span>|  
|<span data-ttu-id="44487-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="44487-108">Level</span></span>|<span data-ttu-id="44487-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="44487-109">Information</span></span>|  
|<span data-ttu-id="44487-110">Канал</span><span class="sxs-lookup"><span data-stu-id="44487-110">Channel</span></span>|<span data-ttu-id="44487-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="44487-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="44487-112">Описание</span><span class="sxs-lookup"><span data-stu-id="44487-112">Description</span></span>  
 <span data-ttu-id="44487-113">Указывает на сбой возобновления закладки.</span><span class="sxs-lookup"><span data-stu-id="44487-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="44487-114">Следующая попытка выполнить операцию получения через буфер будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="44487-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="44487-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="44487-115">Message</span></span>  
 <span data-ttu-id="44487-116">Операция «%2» в экземпляре службы «%1» не может быть выполнена в данный момент.</span><span class="sxs-lookup"><span data-stu-id="44487-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="44487-117">Следующая попытка будет предпринята, когда экземпляр службы будет готов к обработке именно этой операции.</span><span class="sxs-lookup"><span data-stu-id="44487-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="44487-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="44487-118">Details</span></span>  
  
|<span data-ttu-id="44487-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="44487-119">Data Item Name</span></span>|<span data-ttu-id="44487-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="44487-120">Data Item Type</span></span>|<span data-ttu-id="44487-121">Описание</span><span class="sxs-lookup"><span data-stu-id="44487-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="44487-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="44487-122">OperationName</span></span>|<span data-ttu-id="44487-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="44487-123">xs:string</span></span>|<span data-ttu-id="44487-124">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="44487-124">The name of the operation.</span></span>|  
|<span data-ttu-id="44487-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="44487-125">ServiceInstanceId</span></span>|<span data-ttu-id="44487-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="44487-126">xs:string</span></span>|<span data-ttu-id="44487-127">Идентификатор экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="44487-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="44487-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="44487-128">AppDomain</span></span>|<span data-ttu-id="44487-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="44487-129">xs:string</span></span>|<span data-ttu-id="44487-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="44487-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
