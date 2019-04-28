---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 150973935d12455aa671043a619fbd6fd7e77425
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009959"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="6f10c-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="6f10c-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="6f10c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="6f10c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6f10c-104">ID</span><span class="sxs-lookup"><span data-stu-id="6f10c-104">ID</span></span>|<span data-ttu-id="6f10c-105">1131</span><span class="sxs-lookup"><span data-stu-id="6f10c-105">1131</span></span>|  
|<span data-ttu-id="6f10c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6f10c-106">Keywords</span></span>|<span data-ttu-id="6f10c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6f10c-107">WFRuntime</span></span>|  
|<span data-ttu-id="6f10c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="6f10c-108">Level</span></span>|<span data-ttu-id="6f10c-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="6f10c-109">Information</span></span>|  
|<span data-ttu-id="6f10c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="6f10c-110">Channel</span></span>|<span data-ttu-id="6f10c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6f10c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6f10c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6f10c-112">Description</span></span>  
 <span data-ttu-id="6f10c-113">На шаге CacheMetadata действие InvokeMethod указывает на использование асинхронного шаблона при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="6f10c-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6f10c-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="6f10c-114">Message</span></span>  
 <span data-ttu-id="6f10c-115">Метод InvokeMethod «%1»: в методе используется асинхронная модель «%2» и «%3».</span><span class="sxs-lookup"><span data-stu-id="6f10c-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6f10c-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="6f10c-116">Details</span></span>  
  
|<span data-ttu-id="6f10c-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="6f10c-117">Data Item Name</span></span>|<span data-ttu-id="6f10c-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="6f10c-118">Data Item Type</span></span>|<span data-ttu-id="6f10c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="6f10c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6f10c-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="6f10c-120">InvokeMethod</span></span>|<span data-ttu-id="6f10c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6f10c-121">xs:string</span></span>|<span data-ttu-id="6f10c-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="6f10c-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="6f10c-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="6f10c-123">BeginMethod</span></span>|<span data-ttu-id="6f10c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6f10c-124">xs:string</span></span>|<span data-ttu-id="6f10c-125">Имя метода Begin.</span><span class="sxs-lookup"><span data-stu-id="6f10c-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="6f10c-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="6f10c-126">EndMethod</span></span>|<span data-ttu-id="6f10c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="6f10c-127">xs:string</span></span>|<span data-ttu-id="6f10c-128">Имя метода End.</span><span class="sxs-lookup"><span data-stu-id="6f10c-128">The name of the end method.</span></span>|  
|<span data-ttu-id="6f10c-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="6f10c-129">AppDomain</span></span>|<span data-ttu-id="6f10c-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="6f10c-130">xs:string</span></span>|<span data-ttu-id="6f10c-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6f10c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
