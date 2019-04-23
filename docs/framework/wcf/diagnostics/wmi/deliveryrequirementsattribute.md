---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: c81e4b27969d879a70806082f48879cbf1b32ccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979216"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="b8644-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="b8644-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="b8644-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="b8644-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8644-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8644-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b8644-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b8644-105">Methods</span></span>  
 <span data-ttu-id="b8644-106">Класс DeliveryRequirementsAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="b8644-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b8644-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="b8644-107">Properties</span></span>  
 <span data-ttu-id="b8644-108">Класс DeliveryRequirementsAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="b8644-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="b8644-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="b8644-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="b8644-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b8644-110">Data type: string</span></span>  
  
 <span data-ttu-id="b8644-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="b8644-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b8644-112">Указывает, поддерживает ли привязка для службы контракты.</span><span class="sxs-lookup"><span data-stu-id="b8644-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="b8644-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="b8644-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="b8644-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="b8644-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="b8644-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="b8644-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b8644-116">Указывает, поддерживает ли привязка упорядоченные сообщения.</span><span class="sxs-lookup"><span data-stu-id="b8644-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="b8644-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="b8644-117">TargetContract</span></span>  
 <span data-ttu-id="b8644-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b8644-118">Data type: string</span></span>  
  
 <span data-ttu-id="b8644-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="b8644-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b8644-120">Контракт, к которому оно применимо.</span><span class="sxs-lookup"><span data-stu-id="b8644-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8644-121">Требования</span><span class="sxs-lookup"><span data-stu-id="b8644-121">Requirements</span></span>  
  
|<span data-ttu-id="b8644-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b8644-122">MOF</span></span>|<span data-ttu-id="b8644-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b8644-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b8644-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="b8644-124">Namespace</span></span>|<span data-ttu-id="b8644-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="b8644-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8644-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b8644-126">See also</span></span>

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
