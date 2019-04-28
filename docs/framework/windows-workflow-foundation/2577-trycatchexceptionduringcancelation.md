---
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: c272dd91249dfc90e6f4c38a7339919a5a6446e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755627"
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="540f7-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="540f7-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="540f7-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="540f7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="540f7-104">ID</span><span class="sxs-lookup"><span data-stu-id="540f7-104">ID</span></span>|<span data-ttu-id="540f7-105">2577</span><span class="sxs-lookup"><span data-stu-id="540f7-105">2577</span></span>|  
|<span data-ttu-id="540f7-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="540f7-106">Keywords</span></span>|<span data-ttu-id="540f7-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="540f7-107">WFActivities</span></span>|  
|<span data-ttu-id="540f7-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="540f7-108">Level</span></span>|<span data-ttu-id="540f7-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="540f7-109">Warning</span></span>|  
|<span data-ttu-id="540f7-110">Канал</span><span class="sxs-lookup"><span data-stu-id="540f7-110">Channel</span></span>|<span data-ttu-id="540f7-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="540f7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="540f7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="540f7-112">Description</span></span>  
 <span data-ttu-id="540f7-113">Указывает, что дочернее действие для действия TryCatch вызвало исключение во время отмены.</span><span class="sxs-lookup"><span data-stu-id="540f7-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="540f7-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="540f7-114">Message</span></span>  
 <span data-ttu-id="540f7-115">При отмене дочернего действия для действия TryCatch «%1» произошло исключение.</span><span class="sxs-lookup"><span data-stu-id="540f7-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="540f7-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="540f7-116">Details</span></span>  
  
|<span data-ttu-id="540f7-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="540f7-117">Data Item Name</span></span>|<span data-ttu-id="540f7-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="540f7-118">Data Item Type</span></span>|<span data-ttu-id="540f7-119">Описание</span><span class="sxs-lookup"><span data-stu-id="540f7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="540f7-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="540f7-120">DisplayName</span></span>|<span data-ttu-id="540f7-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="540f7-121">xs:string</span></span>|<span data-ttu-id="540f7-122">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="540f7-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="540f7-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="540f7-123">AppDomain</span></span>|<span data-ttu-id="540f7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="540f7-124">xs:string</span></span>|<span data-ttu-id="540f7-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="540f7-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
