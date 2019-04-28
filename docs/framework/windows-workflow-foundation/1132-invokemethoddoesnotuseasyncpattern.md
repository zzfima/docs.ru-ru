---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 64701d4c38c042e8273129be19f9caeb2c442abf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924219"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="48e3b-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="48e3b-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="48e3b-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="48e3b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48e3b-104">ID</span><span class="sxs-lookup"><span data-stu-id="48e3b-104">ID</span></span>|<span data-ttu-id="48e3b-105">1132</span><span class="sxs-lookup"><span data-stu-id="48e3b-105">1132</span></span>|  
|<span data-ttu-id="48e3b-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="48e3b-106">Keywords</span></span>|<span data-ttu-id="48e3b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="48e3b-107">WFRuntime</span></span>|  
|<span data-ttu-id="48e3b-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="48e3b-108">Level</span></span>|<span data-ttu-id="48e3b-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="48e3b-109">Information</span></span>|  
|<span data-ttu-id="48e3b-110">Канал</span><span class="sxs-lookup"><span data-stu-id="48e3b-110">Channel</span></span>|<span data-ttu-id="48e3b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="48e3b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="48e3b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="48e3b-112">Description</span></span>  
 <span data-ttu-id="48e3b-113">На шаге CacheMetadata действие InvokeMethod указывает, что при вызове метода не используется асинхронный шаблон.</span><span class="sxs-lookup"><span data-stu-id="48e3b-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="48e3b-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="48e3b-114">Message</span></span>  
 <span data-ttu-id="48e3b-115">Метод InvokeMethod «%1»: в методе не используется асинхронная модель.</span><span class="sxs-lookup"><span data-stu-id="48e3b-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="48e3b-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="48e3b-116">Details</span></span>  
  
|<span data-ttu-id="48e3b-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="48e3b-117">Data Item Name</span></span>|<span data-ttu-id="48e3b-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="48e3b-118">Data Item Type</span></span>|<span data-ttu-id="48e3b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="48e3b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="48e3b-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="48e3b-120">InvokeMethod</span></span>|<span data-ttu-id="48e3b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="48e3b-121">xs:string</span></span>|<span data-ttu-id="48e3b-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="48e3b-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="48e3b-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="48e3b-123">AppDomain</span></span>|<span data-ttu-id="48e3b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="48e3b-124">xs:string</span></span>|<span data-ttu-id="48e3b-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="48e3b-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
