---
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 714a98a300426d80c3b494d701ae1bd53a49592f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="3ae11-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="3ae11-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="3ae11-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="3ae11-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ae11-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="3ae11-104">ID</span></span>|<span data-ttu-id="3ae11-105">1126</span><span class="sxs-lookup"><span data-stu-id="3ae11-105">1126</span></span>|  
|<span data-ttu-id="3ae11-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ae11-106">Keywords</span></span>|<span data-ttu-id="3ae11-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3ae11-107">WFRuntime</span></span>|  
|<span data-ttu-id="3ae11-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="3ae11-108">Level</span></span>|<span data-ttu-id="3ae11-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="3ae11-109">Information</span></span>|  
|<span data-ttu-id="3ae11-110">Канал</span><span class="sxs-lookup"><span data-stu-id="3ae11-110">Channel</span></span>|<span data-ttu-id="3ae11-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3ae11-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3ae11-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3ae11-112">Description</span></span>  
 <span data-ttu-id="3ae11-113">Означает, что метод, вызванный действием InvokeMethod, привел к созданию исключения.</span><span class="sxs-lookup"><span data-stu-id="3ae11-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3ae11-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="3ae11-114">Message</span></span>  
 <span data-ttu-id="3ae11-115">Возникло исключение в методе, вызванном операцией «%1».</span><span class="sxs-lookup"><span data-stu-id="3ae11-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="3ae11-116">%2</span><span class="sxs-lookup"><span data-stu-id="3ae11-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="3ae11-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="3ae11-117">Details</span></span>  
  
|<span data-ttu-id="3ae11-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="3ae11-118">Data Item Name</span></span>|<span data-ttu-id="3ae11-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="3ae11-119">Data Item Type</span></span>|<span data-ttu-id="3ae11-120">Описание</span><span class="sxs-lookup"><span data-stu-id="3ae11-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3ae11-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="3ae11-121">InvokeMethod</span></span>|<span data-ttu-id="3ae11-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ae11-122">xs:string</span></span>|<span data-ttu-id="3ae11-123">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="3ae11-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="3ae11-124">Исключение</span><span class="sxs-lookup"><span data-stu-id="3ae11-124">Exception</span></span>|<span data-ttu-id="3ae11-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ae11-125">xs:string</span></span>|<span data-ttu-id="3ae11-126">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="3ae11-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="3ae11-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3ae11-127">AppDomain</span></span>|<span data-ttu-id="3ae11-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ae11-128">xs:string</span></span>|<span data-ttu-id="3ae11-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3ae11-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
