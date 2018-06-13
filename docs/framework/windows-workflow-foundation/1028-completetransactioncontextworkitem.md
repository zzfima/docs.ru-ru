---
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 806a437822cef8802a2bef6a54f924f84c88ef60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511391"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="90ac5-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="90ac5-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="90ac5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="90ac5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="90ac5-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="90ac5-104">ID</span></span>|<span data-ttu-id="90ac5-105">1028</span><span class="sxs-lookup"><span data-stu-id="90ac5-105">1028</span></span>|  
|<span data-ttu-id="90ac5-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="90ac5-106">Keywords</span></span>|<span data-ttu-id="90ac5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="90ac5-107">WFRuntime</span></span>|  
|<span data-ttu-id="90ac5-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="90ac5-108">Level</span></span>|<span data-ttu-id="90ac5-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="90ac5-109">Verbose</span></span>|  
|<span data-ttu-id="90ac5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="90ac5-110">Channel</span></span>|<span data-ttu-id="90ac5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="90ac5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="90ac5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="90ac5-112">Description</span></span>  
 <span data-ttu-id="90ac5-113">Указывает на завершение TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="90ac5-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="90ac5-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="90ac5-114">Message</span></span>  
 <span data-ttu-id="90ac5-115">TransactionContextWorkItem завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="90ac5-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="90ac5-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="90ac5-116">Details</span></span>  
  
|<span data-ttu-id="90ac5-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="90ac5-117">Data Item Name</span></span>|<span data-ttu-id="90ac5-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="90ac5-118">Data Item Type</span></span>|<span data-ttu-id="90ac5-119">Описание</span><span class="sxs-lookup"><span data-stu-id="90ac5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="90ac5-120">Действие</span><span class="sxs-lookup"><span data-stu-id="90ac5-120">Activity</span></span>|<span data-ttu-id="90ac5-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="90ac5-121">xs:string</span></span>|<span data-ttu-id="90ac5-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="90ac5-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="90ac5-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="90ac5-123">DisplayName</span></span>|<span data-ttu-id="90ac5-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="90ac5-124">xs:string</span></span>|<span data-ttu-id="90ac5-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="90ac5-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="90ac5-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="90ac5-126">InstanceId</span></span>|<span data-ttu-id="90ac5-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="90ac5-127">xs:string</span></span>|<span data-ttu-id="90ac5-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="90ac5-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="90ac5-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="90ac5-129">AppDomain</span></span>|<span data-ttu-id="90ac5-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="90ac5-130">xs:string</span></span>|<span data-ttu-id="90ac5-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="90ac5-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
