---
title: 1125 - InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: 692c5e56dac0a69ab5705acd284f048391145641
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924270"
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="923ac-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="923ac-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="923ac-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="923ac-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="923ac-104">ID</span><span class="sxs-lookup"><span data-stu-id="923ac-104">ID</span></span>|<span data-ttu-id="923ac-105">1125</span><span class="sxs-lookup"><span data-stu-id="923ac-105">1125</span></span>|  
|<span data-ttu-id="923ac-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="923ac-106">Keywords</span></span>|<span data-ttu-id="923ac-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="923ac-107">WFRuntime</span></span>|  
|<span data-ttu-id="923ac-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="923ac-108">Level</span></span>|<span data-ttu-id="923ac-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="923ac-109">Information</span></span>|  
|<span data-ttu-id="923ac-110">Канал</span><span class="sxs-lookup"><span data-stu-id="923ac-110">Channel</span></span>|<span data-ttu-id="923ac-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="923ac-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="923ac-112">Описание</span><span class="sxs-lookup"><span data-stu-id="923ac-112">Description</span></span>  
 <span data-ttu-id="923ac-113">На шаге CacheMetadata действие InvokeMethod означает, что вызываемый метод - не статический.</span><span class="sxs-lookup"><span data-stu-id="923ac-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="923ac-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="923ac-114">Message</span></span>  
 <span data-ttu-id="923ac-115">Метод InvokeMethod «%1»: метод не является статическим.</span><span class="sxs-lookup"><span data-stu-id="923ac-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="923ac-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="923ac-116">Details</span></span>  
  
|<span data-ttu-id="923ac-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="923ac-117">Data Item Name</span></span>|<span data-ttu-id="923ac-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="923ac-118">Data Item Type</span></span>|<span data-ttu-id="923ac-119">Описание</span><span class="sxs-lookup"><span data-stu-id="923ac-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="923ac-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="923ac-120">InvokeMethod</span></span>|<span data-ttu-id="923ac-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="923ac-121">xs:string</span></span>|<span data-ttu-id="923ac-122">Отображаемое имя действия InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="923ac-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="923ac-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="923ac-123">AppDomain</span></span>|<span data-ttu-id="923ac-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="923ac-124">xs:string</span></span>|<span data-ttu-id="923ac-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="923ac-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
