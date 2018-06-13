---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: d294ba4f14472012b9e311ee53742633b5173f54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485830"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="62132-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="62132-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="62132-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="62132-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62132-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62132-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="62132-105">Методы</span><span class="sxs-lookup"><span data-stu-id="62132-105">Methods</span></span>  
 <span data-ttu-id="62132-106">Класс DeliveryRequirementsAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="62132-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="62132-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="62132-107">Properties</span></span>  
 <span data-ttu-id="62132-108">Класс DeliveryRequirementsAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="62132-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="62132-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="62132-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="62132-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="62132-110">Data type: string</span></span>  
  
 <span data-ttu-id="62132-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="62132-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62132-112">Указывает, поддерживает ли привязка для службы контракты.</span><span class="sxs-lookup"><span data-stu-id="62132-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="62132-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="62132-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="62132-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="62132-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="62132-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="62132-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62132-116">Указывает, поддерживает ли привязка упорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="62132-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="62132-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="62132-117">TargetContract</span></span>  
 <span data-ttu-id="62132-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="62132-118">Data type: string</span></span>  
  
 <span data-ttu-id="62132-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="62132-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62132-120">Контракт, к которому оно применимо.</span><span class="sxs-lookup"><span data-stu-id="62132-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62132-121">Требования</span><span class="sxs-lookup"><span data-stu-id="62132-121">Requirements</span></span>  
  
|<span data-ttu-id="62132-122">MOF</span><span class="sxs-lookup"><span data-stu-id="62132-122">MOF</span></span>|<span data-ttu-id="62132-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="62132-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="62132-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="62132-124">Namespace</span></span>|<span data-ttu-id="62132-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="62132-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62132-126">См. также</span><span class="sxs-lookup"><span data-stu-id="62132-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
