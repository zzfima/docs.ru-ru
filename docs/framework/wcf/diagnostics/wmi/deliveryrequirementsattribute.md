---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: 809e9d809bce456c831aab83c7ac19a882b2959b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571328"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="6a429-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="6a429-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="6a429-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="6a429-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a429-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a429-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6a429-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6a429-105">Methods</span></span>  
 <span data-ttu-id="6a429-106">Класс DeliveryRequirementsAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="6a429-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6a429-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="6a429-107">Properties</span></span>  
 <span data-ttu-id="6a429-108">Класс DeliveryRequirementsAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="6a429-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="6a429-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="6a429-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="6a429-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6a429-110">Data type: string</span></span>  
  
 <span data-ttu-id="6a429-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6a429-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6a429-112">Указывает, поддерживает ли привязка для службы контракты.</span><span class="sxs-lookup"><span data-stu-id="6a429-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="6a429-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="6a429-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="6a429-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="6a429-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="6a429-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6a429-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6a429-116">Указывает, поддерживает ли привязка упорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="6a429-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="6a429-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="6a429-117">TargetContract</span></span>  
 <span data-ttu-id="6a429-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6a429-118">Data type: string</span></span>  
  
 <span data-ttu-id="6a429-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6a429-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6a429-120">Контракт, к которому оно применимо.</span><span class="sxs-lookup"><span data-stu-id="6a429-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a429-121">Требования</span><span class="sxs-lookup"><span data-stu-id="6a429-121">Requirements</span></span>  
  
|<span data-ttu-id="6a429-122">MOF</span><span class="sxs-lookup"><span data-stu-id="6a429-122">MOF</span></span>|<span data-ttu-id="6a429-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6a429-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6a429-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="6a429-124">Namespace</span></span>|<span data-ttu-id="6a429-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="6a429-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a429-126">См. также</span><span class="sxs-lookup"><span data-stu-id="6a429-126">See also</span></span>
- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
