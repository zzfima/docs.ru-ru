---
title: DeliveryRequirementsAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 172f7df4f028c1ddc0f5565e95291e857ee6fa1d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="18d93-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="18d93-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="18d93-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="18d93-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18d93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18d93-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="18d93-105">Методы</span><span class="sxs-lookup"><span data-stu-id="18d93-105">Methods</span></span>  
 <span data-ttu-id="18d93-106">Класс DeliveryRequirementsAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="18d93-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="18d93-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="18d93-107">Properties</span></span>  
 <span data-ttu-id="18d93-108">Класс DeliveryRequirementsAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="18d93-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="18d93-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="18d93-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="18d93-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="18d93-110">Data type: string</span></span>  
  
 <span data-ttu-id="18d93-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="18d93-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18d93-112">Указывает, поддерживает ли привязка для службы контракты.</span><span class="sxs-lookup"><span data-stu-id="18d93-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="18d93-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="18d93-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="18d93-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="18d93-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="18d93-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="18d93-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18d93-116">Указывает, поддерживает ли привязка упорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="18d93-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="18d93-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="18d93-117">TargetContract</span></span>  
 <span data-ttu-id="18d93-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="18d93-118">Data type: string</span></span>  
  
 <span data-ttu-id="18d93-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="18d93-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18d93-120">Контракт, к которому оно применимо.</span><span class="sxs-lookup"><span data-stu-id="18d93-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18d93-121">Требования</span><span class="sxs-lookup"><span data-stu-id="18d93-121">Requirements</span></span>  
  
|<span data-ttu-id="18d93-122">MOF</span><span class="sxs-lookup"><span data-stu-id="18d93-122">MOF</span></span>|<span data-ttu-id="18d93-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="18d93-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="18d93-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="18d93-124">Namespace</span></span>|<span data-ttu-id="18d93-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="18d93-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18d93-126">См. также</span><span class="sxs-lookup"><span data-stu-id="18d93-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
