---
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 714a98a300426d80c3b494d701ae1bd53a49592f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924011"
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="ea5f6-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="ea5f6-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="ea5f6-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ea5f6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ea5f6-104">ID</span><span class="sxs-lookup"><span data-stu-id="ea5f6-104">ID</span></span>|<span data-ttu-id="ea5f6-105">1126</span><span class="sxs-lookup"><span data-stu-id="ea5f6-105">1126</span></span>|  
|<span data-ttu-id="ea5f6-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ea5f6-106">Keywords</span></span>|<span data-ttu-id="ea5f6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ea5f6-107">WFRuntime</span></span>|  
|<span data-ttu-id="ea5f6-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea5f6-108">Level</span></span>|<span data-ttu-id="ea5f6-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="ea5f6-109">Information</span></span>|  
|<span data-ttu-id="ea5f6-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ea5f6-110">Channel</span></span>|<span data-ttu-id="ea5f6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ea5f6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ea5f6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ea5f6-112">Description</span></span>  
 <span data-ttu-id="ea5f6-113">Означает, что метод, вызванный действием InvokeMethod, привел к созданию исключения.</span><span class="sxs-lookup"><span data-stu-id="ea5f6-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ea5f6-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ea5f6-114">Message</span></span>  
 <span data-ttu-id="ea5f6-115">Возникло исключение в методе, вызванном операцией «%1».</span><span class="sxs-lookup"><span data-stu-id="ea5f6-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="ea5f6-116">%2</span><span class="sxs-lookup"><span data-stu-id="ea5f6-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="ea5f6-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ea5f6-117">Details</span></span>  
  
|<span data-ttu-id="ea5f6-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ea5f6-118">Data Item Name</span></span>|<span data-ttu-id="ea5f6-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ea5f6-119">Data Item Type</span></span>|<span data-ttu-id="ea5f6-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ea5f6-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ea5f6-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="ea5f6-121">InvokeMethod</span></span>|<span data-ttu-id="ea5f6-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea5f6-122">xs:string</span></span>|<span data-ttu-id="ea5f6-123">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="ea5f6-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="ea5f6-124">Исключение</span><span class="sxs-lookup"><span data-stu-id="ea5f6-124">Exception</span></span>|<span data-ttu-id="ea5f6-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea5f6-125">xs:string</span></span>|<span data-ttu-id="ea5f6-126">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="ea5f6-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="ea5f6-127">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="ea5f6-127">AppDomain</span></span>|<span data-ttu-id="ea5f6-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea5f6-128">xs:string</span></span>|<span data-ttu-id="ea5f6-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ea5f6-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
