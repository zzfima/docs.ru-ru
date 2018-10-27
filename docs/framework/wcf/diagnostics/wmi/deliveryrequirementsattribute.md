---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: 7bfc03299fffc8070a7d8a4b3885706ea861bdf6
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2018
ms.locfileid: "50042900"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="e964f-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="e964f-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="e964f-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="e964f-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e964f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e964f-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e964f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="e964f-105">Methods</span></span>  
 <span data-ttu-id="e964f-106">Класс DeliveryRequirementsAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="e964f-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e964f-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="e964f-107">Properties</span></span>  
 <span data-ttu-id="e964f-108">Класс DeliveryRequirementsAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="e964f-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="e964f-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="e964f-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="e964f-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="e964f-110">Data type: string</span></span>  
  
 <span data-ttu-id="e964f-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e964f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e964f-112">Указывает, поддерживает ли привязка для службы контракты.</span><span class="sxs-lookup"><span data-stu-id="e964f-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="e964f-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="e964f-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="e964f-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="e964f-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="e964f-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e964f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e964f-116">Указывает, поддерживает ли привязка упорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="e964f-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="e964f-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="e964f-117">TargetContract</span></span>  
 <span data-ttu-id="e964f-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="e964f-118">Data type: string</span></span>  
  
 <span data-ttu-id="e964f-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e964f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e964f-120">Контракт, к которому оно применимо.</span><span class="sxs-lookup"><span data-stu-id="e964f-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e964f-121">Требования</span><span class="sxs-lookup"><span data-stu-id="e964f-121">Requirements</span></span>  
  
|<span data-ttu-id="e964f-122">MOF</span><span class="sxs-lookup"><span data-stu-id="e964f-122">MOF</span></span>|<span data-ttu-id="e964f-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e964f-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e964f-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="e964f-124">Namespace</span></span>|<span data-ttu-id="e964f-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="e964f-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e964f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e964f-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
