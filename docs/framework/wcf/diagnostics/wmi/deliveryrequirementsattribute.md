---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: c81e4b27969d879a70806082f48879cbf1b32ccc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101781"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="378fe-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="378fe-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="378fe-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="378fe-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="378fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="378fe-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="378fe-105">Методы</span><span class="sxs-lookup"><span data-stu-id="378fe-105">Methods</span></span>  
 <span data-ttu-id="378fe-106">Класс DeliveryRequirementsAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="378fe-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="378fe-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="378fe-107">Properties</span></span>  
 <span data-ttu-id="378fe-108">Класс DeliveryRequirementsAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="378fe-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="378fe-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="378fe-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="378fe-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="378fe-110">Data type: string</span></span>  
  
 <span data-ttu-id="378fe-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="378fe-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="378fe-112">Указывает, поддерживает ли привязка для службы контракты.</span><span class="sxs-lookup"><span data-stu-id="378fe-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="378fe-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="378fe-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="378fe-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="378fe-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="378fe-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="378fe-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="378fe-116">Указывает, поддерживает ли привязка упорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="378fe-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="378fe-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="378fe-117">TargetContract</span></span>  
 <span data-ttu-id="378fe-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="378fe-118">Data type: string</span></span>  
  
 <span data-ttu-id="378fe-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="378fe-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="378fe-120">Контракт, к которому оно применимо.</span><span class="sxs-lookup"><span data-stu-id="378fe-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="378fe-121">Требования</span><span class="sxs-lookup"><span data-stu-id="378fe-121">Requirements</span></span>  
  
|<span data-ttu-id="378fe-122">MOF</span><span class="sxs-lookup"><span data-stu-id="378fe-122">MOF</span></span>|<span data-ttu-id="378fe-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="378fe-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="378fe-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="378fe-124">Namespace</span></span>|<span data-ttu-id="378fe-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="378fe-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="378fe-126">См. также</span><span class="sxs-lookup"><span data-stu-id="378fe-126">See also</span></span>

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
