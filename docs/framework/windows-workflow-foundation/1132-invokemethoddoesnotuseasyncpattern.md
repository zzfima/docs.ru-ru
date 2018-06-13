---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 64701d4c38c042e8273129be19f9caeb2c442abf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511880"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="3b5b1-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="3b5b1-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="3b5b1-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="3b5b1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b5b1-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="3b5b1-104">ID</span></span>|<span data-ttu-id="3b5b1-105">1132</span><span class="sxs-lookup"><span data-stu-id="3b5b1-105">1132</span></span>|  
|<span data-ttu-id="3b5b1-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3b5b1-106">Keywords</span></span>|<span data-ttu-id="3b5b1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3b5b1-107">WFRuntime</span></span>|  
|<span data-ttu-id="3b5b1-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="3b5b1-108">Level</span></span>|<span data-ttu-id="3b5b1-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="3b5b1-109">Information</span></span>|  
|<span data-ttu-id="3b5b1-110">Канал</span><span class="sxs-lookup"><span data-stu-id="3b5b1-110">Channel</span></span>|<span data-ttu-id="3b5b1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3b5b1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3b5b1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3b5b1-112">Description</span></span>  
 <span data-ttu-id="3b5b1-113">На шаге CacheMetadata действие InvokeMethod указывает, что при вызове метода не используется асинхронный шаблон.</span><span class="sxs-lookup"><span data-stu-id="3b5b1-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3b5b1-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="3b5b1-114">Message</span></span>  
 <span data-ttu-id="3b5b1-115">Метод InvokeMethod «%1»: в методе не используется асинхронная модель.</span><span class="sxs-lookup"><span data-stu-id="3b5b1-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3b5b1-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="3b5b1-116">Details</span></span>  
  
|<span data-ttu-id="3b5b1-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="3b5b1-117">Data Item Name</span></span>|<span data-ttu-id="3b5b1-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="3b5b1-118">Data Item Type</span></span>|<span data-ttu-id="3b5b1-119">Описание</span><span class="sxs-lookup"><span data-stu-id="3b5b1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3b5b1-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="3b5b1-120">InvokeMethod</span></span>|<span data-ttu-id="3b5b1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b5b1-121">xs:string</span></span>|<span data-ttu-id="3b5b1-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="3b5b1-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="3b5b1-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3b5b1-123">AppDomain</span></span>|<span data-ttu-id="3b5b1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b5b1-124">xs:string</span></span>|<span data-ttu-id="3b5b1-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3b5b1-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
