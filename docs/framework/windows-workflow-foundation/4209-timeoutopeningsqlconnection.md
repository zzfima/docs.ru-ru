---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: d61d710959f99dbc8a91441766a690eb7e9a365c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513169"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="5d9de-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="5d9de-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="5d9de-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="5d9de-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d9de-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="5d9de-104">ID</span></span>|<span data-ttu-id="5d9de-105">4209</span><span class="sxs-lookup"><span data-stu-id="5d9de-105">4209</span></span>|  
|<span data-ttu-id="5d9de-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="5d9de-106">Keywords</span></span>|<span data-ttu-id="5d9de-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="5d9de-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="5d9de-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="5d9de-108">Level</span></span>|<span data-ttu-id="5d9de-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="5d9de-109">Error</span></span>|  
|<span data-ttu-id="5d9de-110">Канал</span><span class="sxs-lookup"><span data-stu-id="5d9de-110">Channel</span></span>|<span data-ttu-id="5d9de-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5d9de-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5d9de-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5d9de-112">Description</span></span>  
 <span data-ttu-id="5d9de-113">Указывает, что при попытке открыть соединение SQL превышено время ожидания.</span><span class="sxs-lookup"><span data-stu-id="5d9de-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5d9de-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="5d9de-114">Message</span></span>  
 <span data-ttu-id="5d9de-115">Истекло время ожидания при открытии соединения SQL.</span><span class="sxs-lookup"><span data-stu-id="5d9de-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="5d9de-116">Не удалось выполнить операцию за выделенное время ожидания %1.</span><span class="sxs-lookup"><span data-stu-id="5d9de-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="5d9de-117">Возможно, выделенное для этой операции время было частью более длительного времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="5d9de-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5d9de-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="5d9de-118">Details</span></span>  
  
|<span data-ttu-id="5d9de-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="5d9de-119">Data Item Name</span></span>|<span data-ttu-id="5d9de-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="5d9de-120">Data Item Type</span></span>|<span data-ttu-id="5d9de-121">Описание</span><span class="sxs-lookup"><span data-stu-id="5d9de-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5d9de-122">Время ожидания</span><span class="sxs-lookup"><span data-stu-id="5d9de-122">Timeout</span></span>|<span data-ttu-id="5d9de-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d9de-123">xs:string</span></span>|<span data-ttu-id="5d9de-124">Значение времени ожидания для открытия соединения SQL.</span><span class="sxs-lookup"><span data-stu-id="5d9de-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="5d9de-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5d9de-125">AppDomain</span></span>|<span data-ttu-id="5d9de-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d9de-126">xs:string</span></span>|<span data-ttu-id="5d9de-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5d9de-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
