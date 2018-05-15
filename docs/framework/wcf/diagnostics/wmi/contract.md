---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 12b45c08a3d8dc69e740ce77d0d2abd097907ac2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="contract"></a><span data-ttu-id="b61e8-102">Контракт</span><span class="sxs-lookup"><span data-stu-id="b61e8-102">Contract</span></span>
<span data-ttu-id="b61e8-103">Контракт</span><span class="sxs-lookup"><span data-stu-id="b61e8-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b61e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b61e8-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="b61e8-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b61e8-105">Methods</span></span>  
 <span data-ttu-id="b61e8-106">Класс контракта не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="b61e8-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b61e8-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="b61e8-107">Properties</span></span>  
 <span data-ttu-id="b61e8-108">Класс контракта имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="b61e8-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="b61e8-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="b61e8-109">AppDomainId</span></span>  
 <span data-ttu-id="b61e8-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="b61e8-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="b61e8-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b61e8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b61e8-112">Идентификатор домена приложения, который размещает контракт.</span><span class="sxs-lookup"><span data-stu-id="b61e8-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="b61e8-113">Расширения функциональности</span><span class="sxs-lookup"><span data-stu-id="b61e8-113">Behaviors</span></span>  
 <span data-ttu-id="b61e8-114">Тип данных: массив Behavior</span><span class="sxs-lookup"><span data-stu-id="b61e8-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="b61e8-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b61e8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b61e8-116">Поведения, связанные с этим контрактом.</span><span class="sxs-lookup"><span data-stu-id="b61e8-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="b61e8-117">name</span><span class="sxs-lookup"><span data-stu-id="b61e8-117">Name</span></span>  
 <span data-ttu-id="b61e8-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b61e8-118">Data type: string</span></span>  
  
 <span data-ttu-id="b61e8-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b61e8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b61e8-120">Имя контракта в WSDL.</span><span class="sxs-lookup"><span data-stu-id="b61e8-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="b61e8-121">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="b61e8-121">Namespace</span></span>  
 <span data-ttu-id="b61e8-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b61e8-122">Data type: string</span></span>  
  
 <span data-ttu-id="b61e8-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b61e8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b61e8-124">Пространство имен элемента `portType` в WSDL.</span><span class="sxs-lookup"><span data-stu-id="b61e8-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="b61e8-125">Операции</span><span class="sxs-lookup"><span data-stu-id="b61e8-125">Operations</span></span>  
 <span data-ttu-id="b61e8-126">Тип данных: массив Operation</span><span class="sxs-lookup"><span data-stu-id="b61e8-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="b61e8-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b61e8-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b61e8-128">Операции данного контракта.</span><span class="sxs-lookup"><span data-stu-id="b61e8-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="b61e8-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="b61e8-129">ProcessId</span></span>  
 <span data-ttu-id="b61e8-130">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="b61e8-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="b61e8-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b61e8-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b61e8-132">Идентификатор процесса, который размещает контракт.</span><span class="sxs-lookup"><span data-stu-id="b61e8-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="b61e8-133">ref</span><span class="sxs-lookup"><span data-stu-id="b61e8-133">ref</span></span>  
 <span data-ttu-id="b61e8-134">Тип данных: Contract</span><span class="sxs-lookup"><span data-stu-id="b61e8-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="b61e8-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b61e8-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b61e8-136">Тип обратного вызова, когда контракт является дуплексным.</span><span class="sxs-lookup"><span data-stu-id="b61e8-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="b61e8-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="b61e8-137">SessionMode</span></span>  
 <span data-ttu-id="b61e8-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b61e8-138">Data type: string</span></span>  
  
 <span data-ttu-id="b61e8-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b61e8-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b61e8-140">Указывает, требуется ли для контракта, чтобы связанная с ним привязка использовала сеансы канала.</span><span class="sxs-lookup"><span data-stu-id="b61e8-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="b61e8-141">Тип</span><span class="sxs-lookup"><span data-stu-id="b61e8-141">Type</span></span>  
 <span data-ttu-id="b61e8-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b61e8-142">Data type: string</span></span>  
  
 <span data-ttu-id="b61e8-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b61e8-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b61e8-144">Тип контракта.</span><span class="sxs-lookup"><span data-stu-id="b61e8-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b61e8-145">Требования</span><span class="sxs-lookup"><span data-stu-id="b61e8-145">Requirements</span></span>  
  
|<span data-ttu-id="b61e8-146">MOF</span><span class="sxs-lookup"><span data-stu-id="b61e8-146">MOF</span></span>|<span data-ttu-id="b61e8-147">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b61e8-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b61e8-148">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="b61e8-148">Namespace</span></span>|<span data-ttu-id="b61e8-149">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="b61e8-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b61e8-150">См. также</span><span class="sxs-lookup"><span data-stu-id="b61e8-150">See Also</span></span>  
 <xref:System.ServiceModel.Description.ContractDescription>
