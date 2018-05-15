---
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: c272dd91249dfc90e6f4c38a7339919a5a6446e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="f7e0b-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="f7e0b-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="f7e0b-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f7e0b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f7e0b-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="f7e0b-104">ID</span></span>|<span data-ttu-id="f7e0b-105">2577</span><span class="sxs-lookup"><span data-stu-id="f7e0b-105">2577</span></span>|  
|<span data-ttu-id="f7e0b-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f7e0b-106">Keywords</span></span>|<span data-ttu-id="f7e0b-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="f7e0b-107">WFActivities</span></span>|  
|<span data-ttu-id="f7e0b-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f7e0b-108">Level</span></span>|<span data-ttu-id="f7e0b-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="f7e0b-109">Warning</span></span>|  
|<span data-ttu-id="f7e0b-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f7e0b-110">Channel</span></span>|<span data-ttu-id="f7e0b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f7e0b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f7e0b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f7e0b-112">Description</span></span>  
 <span data-ttu-id="f7e0b-113">Указывает, что дочернее действие для действия TryCatch вызвало исключение во время отмены.</span><span class="sxs-lookup"><span data-stu-id="f7e0b-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f7e0b-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f7e0b-114">Message</span></span>  
 <span data-ttu-id="f7e0b-115">При отмене дочернего действия для действия TryCatch «%1» произошло исключение.</span><span class="sxs-lookup"><span data-stu-id="f7e0b-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f7e0b-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f7e0b-116">Details</span></span>  
  
|<span data-ttu-id="f7e0b-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f7e0b-117">Data Item Name</span></span>|<span data-ttu-id="f7e0b-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f7e0b-118">Data Item Type</span></span>|<span data-ttu-id="f7e0b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f7e0b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f7e0b-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f7e0b-120">DisplayName</span></span>|<span data-ttu-id="f7e0b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7e0b-121">xs:string</span></span>|<span data-ttu-id="f7e0b-122">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="f7e0b-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="f7e0b-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f7e0b-123">AppDomain</span></span>|<span data-ttu-id="f7e0b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f7e0b-124">xs:string</span></span>|<span data-ttu-id="f7e0b-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f7e0b-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
