---
title: 4209 - TimeoutOpeningSqlConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f87e99585ccbdf3b89653f026860e7b66dc6c9b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="57df9-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="57df9-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="57df9-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="57df9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57df9-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="57df9-104">ID</span></span>|<span data-ttu-id="57df9-105">4209</span><span class="sxs-lookup"><span data-stu-id="57df9-105">4209</span></span>|  
|<span data-ttu-id="57df9-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="57df9-106">Keywords</span></span>|<span data-ttu-id="57df9-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="57df9-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="57df9-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="57df9-108">Level</span></span>|<span data-ttu-id="57df9-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="57df9-109">Error</span></span>|  
|<span data-ttu-id="57df9-110">Канал</span><span class="sxs-lookup"><span data-stu-id="57df9-110">Channel</span></span>|<span data-ttu-id="57df9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="57df9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="57df9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="57df9-112">Description</span></span>  
 <span data-ttu-id="57df9-113">Указывает, что при попытке открыть соединение SQL превышено время ожидания.</span><span class="sxs-lookup"><span data-stu-id="57df9-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="57df9-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="57df9-114">Message</span></span>  
 <span data-ttu-id="57df9-115">Истекло время ожидания при открытии соединения SQL.</span><span class="sxs-lookup"><span data-stu-id="57df9-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="57df9-116">Не удалось выполнить операцию за выделенное время ожидания %1.</span><span class="sxs-lookup"><span data-stu-id="57df9-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="57df9-117">Возможно, выделенное для этой операции время было частью более длительного времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="57df9-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="57df9-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="57df9-118">Details</span></span>  
  
|<span data-ttu-id="57df9-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="57df9-119">Data Item Name</span></span>|<span data-ttu-id="57df9-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="57df9-120">Data Item Type</span></span>|<span data-ttu-id="57df9-121">Описание</span><span class="sxs-lookup"><span data-stu-id="57df9-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="57df9-122">Время ожидания</span><span class="sxs-lookup"><span data-stu-id="57df9-122">Timeout</span></span>|<span data-ttu-id="57df9-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="57df9-123">xs:string</span></span>|<span data-ttu-id="57df9-124">Значение времени ожидания для открытия соединения SQL.</span><span class="sxs-lookup"><span data-stu-id="57df9-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="57df9-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="57df9-125">AppDomain</span></span>|<span data-ttu-id="57df9-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="57df9-126">xs:string</span></span>|<span data-ttu-id="57df9-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="57df9-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
