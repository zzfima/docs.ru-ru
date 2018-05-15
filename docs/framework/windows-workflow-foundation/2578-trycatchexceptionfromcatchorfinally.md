---
title: 2578 - TryCatchExceptionFromCatchOrFinally
ms.date: 03/30/2017
ms.assetid: 4803fee6-b8d8-4937-9907-d5c5fd5299db
ms.openlocfilehash: 46fb52e665d49ed7a0336dbeeb6ed07f0d479fb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="2578---trycatchexceptionfromcatchorfinally"></a><span data-ttu-id="2707f-102">2578 - TryCatchExceptionFromCatchOrFinally</span><span class="sxs-lookup"><span data-stu-id="2707f-102">2578 - TryCatchExceptionFromCatchOrFinally</span></span>
## <a name="properties"></a><span data-ttu-id="2707f-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="2707f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2707f-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="2707f-104">ID</span></span>|<span data-ttu-id="2707f-105">2578</span><span class="sxs-lookup"><span data-stu-id="2707f-105">2578</span></span>|  
|<span data-ttu-id="2707f-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2707f-106">Keywords</span></span>|<span data-ttu-id="2707f-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="2707f-107">WFActivities</span></span>|  
|<span data-ttu-id="2707f-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="2707f-108">Level</span></span>|<span data-ttu-id="2707f-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="2707f-109">Warning</span></span>|  
|<span data-ttu-id="2707f-110">Канал</span><span class="sxs-lookup"><span data-stu-id="2707f-110">Channel</span></span>|<span data-ttu-id="2707f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2707f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2707f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2707f-112">Description</span></span>  
 <span data-ttu-id="2707f-113">Указывает, что действие Catch или Finally вызвало исключение.</span><span class="sxs-lookup"><span data-stu-id="2707f-113">Indicates a Catch or Finally activity has thrown an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2707f-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2707f-114">Message</span></span>  
 <span data-ttu-id="2707f-115">В действии Catch или Finally, связанном с действием TryCatch «%1», произошло исключение.</span><span class="sxs-lookup"><span data-stu-id="2707f-115">A Catch or Finally activity that is associated with the TryCatch activity '%1' has thrown an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2707f-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="2707f-116">Details</span></span>  
  
|<span data-ttu-id="2707f-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="2707f-117">Data Item Name</span></span>|<span data-ttu-id="2707f-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="2707f-118">Data Item Type</span></span>|<span data-ttu-id="2707f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="2707f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2707f-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2707f-120">DisplayName</span></span>|<span data-ttu-id="2707f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2707f-121">xs:string</span></span>|<span data-ttu-id="2707f-122">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="2707f-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="2707f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2707f-123">AppDomain</span></span>|<span data-ttu-id="2707f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2707f-124">xs:string</span></span>|<span data-ttu-id="2707f-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2707f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
