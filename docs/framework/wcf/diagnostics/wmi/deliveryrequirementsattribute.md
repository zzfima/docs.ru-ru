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
ms.workload: dotnet
ms.openlocfilehash: e297bfc0499ea3ee8d3dd8395165ca22b2baa1de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="7a842-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="7a842-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="7a842-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="7a842-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a842-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a842-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7a842-105">Методы</span><span class="sxs-lookup"><span data-stu-id="7a842-105">Methods</span></span>  
 <span data-ttu-id="7a842-106">Класс DeliveryRequirementsAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="7a842-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7a842-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="7a842-107">Properties</span></span>  
 <span data-ttu-id="7a842-108">Класс DeliveryRequirementsAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="7a842-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="7a842-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="7a842-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="7a842-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="7a842-110">Data type: string</span></span>  
  
 <span data-ttu-id="7a842-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="7a842-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a842-112">Указывает, поддерживает ли привязка для службы контракты.</span><span class="sxs-lookup"><span data-stu-id="7a842-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="7a842-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="7a842-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="7a842-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="7a842-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="7a842-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="7a842-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a842-116">Указывает, поддерживает ли привязка упорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="7a842-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="7a842-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="7a842-117">TargetContract</span></span>  
 <span data-ttu-id="7a842-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="7a842-118">Data type: string</span></span>  
  
 <span data-ttu-id="7a842-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="7a842-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7a842-120">Контракт, к которому оно применимо.</span><span class="sxs-lookup"><span data-stu-id="7a842-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a842-121">Требования</span><span class="sxs-lookup"><span data-stu-id="7a842-121">Requirements</span></span>  
  
|<span data-ttu-id="7a842-122">MOF</span><span class="sxs-lookup"><span data-stu-id="7a842-122">MOF</span></span>|<span data-ttu-id="7a842-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7a842-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7a842-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="7a842-124">Namespace</span></span>|<span data-ttu-id="7a842-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="7a842-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a842-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7a842-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
