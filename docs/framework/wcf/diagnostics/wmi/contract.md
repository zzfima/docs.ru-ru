---
title: Контракт
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: e4a21e95a6f1f1860ed36c968d17bb8ac8465dce
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68868432"
---
# <a name="contract"></a><span data-ttu-id="9ae4d-102">Контракт</span><span class="sxs-lookup"><span data-stu-id="9ae4d-102">Contract</span></span>
<span data-ttu-id="9ae4d-103">Контракт</span><span class="sxs-lookup"><span data-stu-id="9ae4d-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ae4d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ae4d-104">Syntax</span></span>  
  
```csharp
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9ae4d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9ae4d-105">Methods</span></span>  
 <span data-ttu-id="9ae4d-106">Класс контракта не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="9ae4d-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9ae4d-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="9ae4d-107">Properties</span></span>  
 <span data-ttu-id="9ae4d-108">Класс контракта имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="9ae4d-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="9ae4d-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="9ae4d-109">AppDomainId</span></span>  
 <span data-ttu-id="9ae4d-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="9ae4d-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="9ae4d-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ae4d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ae4d-112">Идентификатор домена приложения, который размещает контракт.</span><span class="sxs-lookup"><span data-stu-id="9ae4d-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="9ae4d-113">поведения</span><span class="sxs-lookup"><span data-stu-id="9ae4d-113">Behaviors</span></span>  
 <span data-ttu-id="9ae4d-114">Тип данных: Массив поведений</span><span class="sxs-lookup"><span data-stu-id="9ae4d-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="9ae4d-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ae4d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ae4d-116">Поведения, связанные с этим контрактом.</span><span class="sxs-lookup"><span data-stu-id="9ae4d-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="9ae4d-117">name</span><span class="sxs-lookup"><span data-stu-id="9ae4d-117">Name</span></span>  
 <span data-ttu-id="9ae4d-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="9ae4d-118">Data type: string</span></span>  
  
 <span data-ttu-id="9ae4d-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ae4d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ae4d-120">Имя контракта в WSDL.</span><span class="sxs-lookup"><span data-stu-id="9ae4d-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="9ae4d-121">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="9ae4d-121">Namespace</span></span>  
 <span data-ttu-id="9ae4d-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="9ae4d-122">Data type: string</span></span>  
  
 <span data-ttu-id="9ae4d-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ae4d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ae4d-124">Пространство имен элемента `portType` в WSDL.</span><span class="sxs-lookup"><span data-stu-id="9ae4d-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="9ae4d-125">Операции</span><span class="sxs-lookup"><span data-stu-id="9ae4d-125">Operations</span></span>  
 <span data-ttu-id="9ae4d-126">Тип данных: Массив операций</span><span class="sxs-lookup"><span data-stu-id="9ae4d-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="9ae4d-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ae4d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ae4d-128">Операции данного контракта.</span><span class="sxs-lookup"><span data-stu-id="9ae4d-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="9ae4d-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="9ae4d-129">ProcessId</span></span>  
 <span data-ttu-id="9ae4d-130">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="9ae4d-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="9ae4d-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ae4d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ae4d-132">Идентификатор процесса, который размещает контракт.</span><span class="sxs-lookup"><span data-stu-id="9ae4d-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="9ae4d-133">ref</span><span class="sxs-lookup"><span data-stu-id="9ae4d-133">ref</span></span>  
 <span data-ttu-id="9ae4d-134">Тип данных: Контракт</span><span class="sxs-lookup"><span data-stu-id="9ae4d-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="9ae4d-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ae4d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ae4d-136">Тип обратного вызова, когда контракт является дуплексным.</span><span class="sxs-lookup"><span data-stu-id="9ae4d-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="9ae4d-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="9ae4d-137">SessionMode</span></span>  
 <span data-ttu-id="9ae4d-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="9ae4d-138">Data type: string</span></span>  
  
 <span data-ttu-id="9ae4d-139">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ae4d-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ae4d-140">Указывает, требуется ли для контракта, чтобы связанная с ним привязка использовала сеансы канала.</span><span class="sxs-lookup"><span data-stu-id="9ae4d-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="9ae4d-141">Тип</span><span class="sxs-lookup"><span data-stu-id="9ae4d-141">Type</span></span>  
 <span data-ttu-id="9ae4d-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="9ae4d-142">Data type: string</span></span>  
  
 <span data-ttu-id="9ae4d-143">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ae4d-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ae4d-144">Тип контракта.</span><span class="sxs-lookup"><span data-stu-id="9ae4d-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ae4d-145">Требования</span><span class="sxs-lookup"><span data-stu-id="9ae4d-145">Requirements</span></span>  
  
|<span data-ttu-id="9ae4d-146">MOF</span><span class="sxs-lookup"><span data-stu-id="9ae4d-146">MOF</span></span>|<span data-ttu-id="9ae4d-147">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9ae4d-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9ae4d-148">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="9ae4d-148">Namespace</span></span>|<span data-ttu-id="9ae4d-149">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="9ae4d-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ae4d-150">См. также</span><span class="sxs-lookup"><span data-stu-id="9ae4d-150">See also</span></span>

- <xref:System.ServiceModel.Description.ContractDescription>
