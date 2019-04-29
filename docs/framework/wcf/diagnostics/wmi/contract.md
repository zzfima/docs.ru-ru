---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 10789f9a2940c239ae20c8fd1e9d48bca0e820ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963700"
---
# <a name="contract"></a><span data-ttu-id="6d621-102">Контракт</span><span class="sxs-lookup"><span data-stu-id="6d621-102">Contract</span></span>
<span data-ttu-id="6d621-103">Контракт</span><span class="sxs-lookup"><span data-stu-id="6d621-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d621-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d621-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="6d621-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6d621-105">Methods</span></span>  
 <span data-ttu-id="6d621-106">Класс контракта не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="6d621-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6d621-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="6d621-107">Properties</span></span>  
 <span data-ttu-id="6d621-108">Класс контракта имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="6d621-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="6d621-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="6d621-109">AppDomainId</span></span>  
 <span data-ttu-id="6d621-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="6d621-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="6d621-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6d621-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6d621-112">Идентификатор домена приложения, который размещает контракт.</span><span class="sxs-lookup"><span data-stu-id="6d621-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="6d621-113">поведения</span><span class="sxs-lookup"><span data-stu-id="6d621-113">Behaviors</span></span>  
 <span data-ttu-id="6d621-114">Тип данных: Массив Behavior</span><span class="sxs-lookup"><span data-stu-id="6d621-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="6d621-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6d621-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6d621-116">Поведения, связанные с этим контрактом.</span><span class="sxs-lookup"><span data-stu-id="6d621-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="6d621-117">name</span><span class="sxs-lookup"><span data-stu-id="6d621-117">Name</span></span>  
 <span data-ttu-id="6d621-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6d621-118">Data type: string</span></span>  
  
 <span data-ttu-id="6d621-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6d621-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6d621-120">Имя контракта в WSDL.</span><span class="sxs-lookup"><span data-stu-id="6d621-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="6d621-121">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="6d621-121">Namespace</span></span>  
 <span data-ttu-id="6d621-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6d621-122">Data type: string</span></span>  
  
 <span data-ttu-id="6d621-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6d621-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6d621-124">Пространство имен элемента `portType` в WSDL.</span><span class="sxs-lookup"><span data-stu-id="6d621-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="6d621-125">Операции</span><span class="sxs-lookup"><span data-stu-id="6d621-125">Operations</span></span>  
 <span data-ttu-id="6d621-126">Тип данных: Массив Operation</span><span class="sxs-lookup"><span data-stu-id="6d621-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="6d621-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6d621-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6d621-128">Операции данного контракта.</span><span class="sxs-lookup"><span data-stu-id="6d621-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="6d621-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="6d621-129">ProcessId</span></span>  
 <span data-ttu-id="6d621-130">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="6d621-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="6d621-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6d621-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6d621-132">Идентификатор процесса, который размещает контракт.</span><span class="sxs-lookup"><span data-stu-id="6d621-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="6d621-133">ref</span><span class="sxs-lookup"><span data-stu-id="6d621-133">ref</span></span>  
 <span data-ttu-id="6d621-134">Тип данных: Контракт</span><span class="sxs-lookup"><span data-stu-id="6d621-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="6d621-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6d621-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6d621-136">Тип обратного вызова, когда контракт является дуплексным.</span><span class="sxs-lookup"><span data-stu-id="6d621-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="6d621-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="6d621-137">SessionMode</span></span>  
 <span data-ttu-id="6d621-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6d621-138">Data type: string</span></span>  
  
 <span data-ttu-id="6d621-139">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6d621-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6d621-140">Указывает, требуется ли для контракта, чтобы связанная с ним привязка использовала сеансы канала.</span><span class="sxs-lookup"><span data-stu-id="6d621-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="6d621-141">Тип</span><span class="sxs-lookup"><span data-stu-id="6d621-141">Type</span></span>  
 <span data-ttu-id="6d621-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="6d621-142">Data type: string</span></span>  
  
 <span data-ttu-id="6d621-143">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="6d621-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6d621-144">Тип контракта.</span><span class="sxs-lookup"><span data-stu-id="6d621-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d621-145">Требования</span><span class="sxs-lookup"><span data-stu-id="6d621-145">Requirements</span></span>  
  
|<span data-ttu-id="6d621-146">MOF</span><span class="sxs-lookup"><span data-stu-id="6d621-146">MOF</span></span>|<span data-ttu-id="6d621-147">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6d621-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6d621-148">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="6d621-148">Namespace</span></span>|<span data-ttu-id="6d621-149">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="6d621-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d621-150">См. также</span><span class="sxs-lookup"><span data-stu-id="6d621-150">See also</span></span>

- <xref:System.ServiceModel.Description.ContractDescription>
