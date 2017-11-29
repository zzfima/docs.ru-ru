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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a3fb3c780b80172db8770e717f517b97608fcb7c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="4210---sqlexceptioncaught"></a><span data-ttu-id="2237f-102">4210 - SqlExceptionCaught</span><span class="sxs-lookup"><span data-stu-id="2237f-102">4210 - SqlExceptionCaught</span></span>
## <a name="properties"></a><span data-ttu-id="2237f-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2237f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2237f-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="2237f-104">ID</span></span>|<span data-ttu-id="2237f-105">4210</span><span class="sxs-lookup"><span data-stu-id="2237f-105">4210</span></span>|  
|<span data-ttu-id="2237f-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2237f-106">Keywords</span></span>|<span data-ttu-id="2237f-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="2237f-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="2237f-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="2237f-108">Level</span></span>|<span data-ttu-id="2237f-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="2237f-109">Warning</span></span>|  
|<span data-ttu-id="2237f-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2237f-110">Channel</span></span>|<span data-ttu-id="2237f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2237f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2237f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2237f-112">Description</span></span>  
 <span data-ttu-id="2237f-113">Указывает, что было перехвачено исключение SQL.</span><span class="sxs-lookup"><span data-stu-id="2237f-113">Indicates a SQL exception was caught.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2237f-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2237f-114">Message</span></span>  
 <span data-ttu-id="2237f-115">Обнаружено исключение SQL с номером %1, сообщение %2.</span><span class="sxs-lookup"><span data-stu-id="2237f-115">Caught SQL Exception number %1 message %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2237f-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="2237f-116">Details</span></span>  
  
|<span data-ttu-id="2237f-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="2237f-117">Data Item Name</span></span>|<span data-ttu-id="2237f-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="2237f-118">Data Item Type</span></span>|<span data-ttu-id="2237f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="2237f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2237f-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="2237f-120">ErrorNumber</span></span>|<span data-ttu-id="2237f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2237f-121">xs:string</span></span>|<span data-ttu-id="2237f-122">Номер ошибки SQL.</span><span class="sxs-lookup"><span data-stu-id="2237f-122">The SQL error number.</span></span>|  
|<span data-ttu-id="2237f-123">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="2237f-123">ExceptionMessage</span></span>|<span data-ttu-id="2237f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2237f-124">xs:string</span></span>|<span data-ttu-id="2237f-125">Текст сообщения из исключения SQL.</span><span class="sxs-lookup"><span data-stu-id="2237f-125">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="2237f-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2237f-126">AppDomain</span></span>|<span data-ttu-id="2237f-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="2237f-127">xs:string</span></span>|<span data-ttu-id="2237f-128">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2237f-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
