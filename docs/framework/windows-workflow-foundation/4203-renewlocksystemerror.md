---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 984f7ddae8797cba17753a618d0820d21bde5eef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513933"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="918e5-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="918e5-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="918e5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="918e5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="918e5-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="918e5-104">ID</span></span>|<span data-ttu-id="918e5-105">4203</span><span class="sxs-lookup"><span data-stu-id="918e5-105">4203</span></span>|  
|<span data-ttu-id="918e5-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="918e5-106">Keywords</span></span>|<span data-ttu-id="918e5-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="918e5-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="918e5-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="918e5-108">Level</span></span>|<span data-ttu-id="918e5-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="918e5-109">Error</span></span>|  
|<span data-ttu-id="918e5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="918e5-110">Channel</span></span>|<span data-ttu-id="918e5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="918e5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="918e5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="918e5-112">Description</span></span>  
 <span data-ttu-id="918e5-113">Указывает, что поставщику SQL не удалось продлить срок блокировки либо из-за того, что срок блокировки уже истек, либо из-за того, что владелец блокировки был удален.</span><span class="sxs-lookup"><span data-stu-id="918e5-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="918e5-114">SqlWorkflowInstanceStore будет прервано.</span><span class="sxs-lookup"><span data-stu-id="918e5-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="918e5-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="918e5-115">Message</span></span>  
 <span data-ttu-id="918e5-116">Не удалось увеличить срок окончания блокировки, срок окончания блокировки уже истек или владелец блокировки удален.</span><span class="sxs-lookup"><span data-stu-id="918e5-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="918e5-117">Прерывание блокировки SqlWorkflowInstanceStore.</span><span class="sxs-lookup"><span data-stu-id="918e5-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="918e5-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="918e5-118">Details</span></span>  
  
|<span data-ttu-id="918e5-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="918e5-119">Data Item Name</span></span>|<span data-ttu-id="918e5-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="918e5-120">Data Item Type</span></span>|<span data-ttu-id="918e5-121">Описание</span><span class="sxs-lookup"><span data-stu-id="918e5-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="918e5-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="918e5-122">AppDomain</span></span>|<span data-ttu-id="918e5-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="918e5-123">xs:string</span></span>|<span data-ttu-id="918e5-124">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="918e5-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
