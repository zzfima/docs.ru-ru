---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ede74eb642c5c2c79b90cf1458db424d9f83b087
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774248"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="f6c9c-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="f6c9c-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="f6c9c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f6c9c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6c9c-104">ID</span><span class="sxs-lookup"><span data-stu-id="f6c9c-104">ID</span></span>|<span data-ttu-id="f6c9c-105">4211</span><span class="sxs-lookup"><span data-stu-id="f6c9c-105">4211</span></span>|  
|<span data-ttu-id="f6c9c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f6c9c-106">Keywords</span></span>|<span data-ttu-id="f6c9c-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="f6c9c-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="f6c9c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f6c9c-108">Level</span></span>|<span data-ttu-id="f6c9c-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="f6c9c-109">Warning</span></span>|  
|<span data-ttu-id="f6c9c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f6c9c-110">Channel</span></span>|<span data-ttu-id="f6c9c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f6c9c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f6c9c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f6c9c-112">Description</span></span>  
 <span data-ttu-id="f6c9c-113">Указывает на повтор SQL с задержкой.</span><span class="sxs-lookup"><span data-stu-id="f6c9c-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f6c9c-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f6c9c-114">Message</span></span>  
 <span data-ttu-id="f6c9c-115">Повторная попытка поместить SQL в очередь с задержкой %1 мс.</span><span class="sxs-lookup"><span data-stu-id="f6c9c-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f6c9c-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f6c9c-116">Details</span></span>  
  
|<span data-ttu-id="f6c9c-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f6c9c-117">Data Item Name</span></span>|<span data-ttu-id="f6c9c-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f6c9c-118">Data Item Type</span></span>|<span data-ttu-id="f6c9c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f6c9c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f6c9c-120">Задержка</span><span class="sxs-lookup"><span data-stu-id="f6c9c-120">Delay</span></span>|<span data-ttu-id="f6c9c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f6c9c-121">xs:string</span></span>|<span data-ttu-id="f6c9c-122">Задержка между попытками.</span><span class="sxs-lookup"><span data-stu-id="f6c9c-122">The delay between retries.</span></span>|  
|<span data-ttu-id="f6c9c-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="f6c9c-123">AppDomain</span></span>|<span data-ttu-id="f6c9c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f6c9c-124">xs:string</span></span>|<span data-ttu-id="f6c9c-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f6c9c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
