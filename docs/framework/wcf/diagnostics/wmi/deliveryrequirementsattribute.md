---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: 7bfc03299fffc8070a7d8a4b3885706ea861bdf6
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198519"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="4fbf7-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="4fbf7-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="4fbf7-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="4fbf7-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fbf7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4fbf7-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4fbf7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4fbf7-105">Methods</span></span>  
 <span data-ttu-id="4fbf7-106">Класс DeliveryRequirementsAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="4fbf7-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4fbf7-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="4fbf7-107">Properties</span></span>  
 <span data-ttu-id="4fbf7-108">Класс DeliveryRequirementsAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="4fbf7-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="4fbf7-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="4fbf7-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="4fbf7-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="4fbf7-110">Data type: string</span></span>  
  
 <span data-ttu-id="4fbf7-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4fbf7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fbf7-112">Указывает, поддерживает ли привязка для службы контракты.</span><span class="sxs-lookup"><span data-stu-id="4fbf7-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="4fbf7-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="4fbf7-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="4fbf7-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="4fbf7-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="4fbf7-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4fbf7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fbf7-116">Указывает, поддерживает ли привязка упорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="4fbf7-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="4fbf7-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="4fbf7-117">TargetContract</span></span>  
 <span data-ttu-id="4fbf7-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="4fbf7-118">Data type: string</span></span>  
  
 <span data-ttu-id="4fbf7-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4fbf7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4fbf7-120">Контракт, к которому оно применимо.</span><span class="sxs-lookup"><span data-stu-id="4fbf7-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fbf7-121">Требования</span><span class="sxs-lookup"><span data-stu-id="4fbf7-121">Requirements</span></span>  
  
|<span data-ttu-id="4fbf7-122">MOF</span><span class="sxs-lookup"><span data-stu-id="4fbf7-122">MOF</span></span>|<span data-ttu-id="4fbf7-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4fbf7-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4fbf7-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="4fbf7-124">Namespace</span></span>|<span data-ttu-id="4fbf7-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="4fbf7-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4fbf7-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4fbf7-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
