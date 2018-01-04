---
title: 4210 - SqlExceptionCaught
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fbcb566574e38e3c4688c16bd29a33ff7048bfa4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="4210---sqlexceptioncaught"></a><span data-ttu-id="10ef1-102">4210 - SqlExceptionCaught</span><span class="sxs-lookup"><span data-stu-id="10ef1-102">4210 - SqlExceptionCaught</span></span>
## <a name="properties"></a><span data-ttu-id="10ef1-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="10ef1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10ef1-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="10ef1-104">ID</span></span>|<span data-ttu-id="10ef1-105">4210</span><span class="sxs-lookup"><span data-stu-id="10ef1-105">4210</span></span>|  
|<span data-ttu-id="10ef1-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="10ef1-106">Keywords</span></span>|<span data-ttu-id="10ef1-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="10ef1-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="10ef1-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="10ef1-108">Level</span></span>|<span data-ttu-id="10ef1-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="10ef1-109">Warning</span></span>|  
|<span data-ttu-id="10ef1-110">Канал</span><span class="sxs-lookup"><span data-stu-id="10ef1-110">Channel</span></span>|<span data-ttu-id="10ef1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="10ef1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="10ef1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="10ef1-112">Description</span></span>  
 <span data-ttu-id="10ef1-113">Указывает, что было перехвачено исключение SQL.</span><span class="sxs-lookup"><span data-stu-id="10ef1-113">Indicates a SQL exception was caught.</span></span>  
  
## <a name="message"></a><span data-ttu-id="10ef1-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="10ef1-114">Message</span></span>  
 <span data-ttu-id="10ef1-115">Обнаружено исключение SQL с номером %1, сообщение %2.</span><span class="sxs-lookup"><span data-stu-id="10ef1-115">Caught SQL Exception number %1 message %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="10ef1-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="10ef1-116">Details</span></span>  
  
|<span data-ttu-id="10ef1-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="10ef1-117">Data Item Name</span></span>|<span data-ttu-id="10ef1-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="10ef1-118">Data Item Type</span></span>|<span data-ttu-id="10ef1-119">Описание</span><span class="sxs-lookup"><span data-stu-id="10ef1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="10ef1-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="10ef1-120">ErrorNumber</span></span>|<span data-ttu-id="10ef1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="10ef1-121">xs:string</span></span>|<span data-ttu-id="10ef1-122">Номер ошибки SQL.</span><span class="sxs-lookup"><span data-stu-id="10ef1-122">The SQL error number.</span></span>|  
|<span data-ttu-id="10ef1-123">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="10ef1-123">ExceptionMessage</span></span>|<span data-ttu-id="10ef1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="10ef1-124">xs:string</span></span>|<span data-ttu-id="10ef1-125">Текст сообщения из исключения SQL.</span><span class="sxs-lookup"><span data-stu-id="10ef1-125">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="10ef1-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="10ef1-126">AppDomain</span></span>|<span data-ttu-id="10ef1-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="10ef1-127">xs:string</span></span>|<span data-ttu-id="10ef1-128">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="10ef1-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
