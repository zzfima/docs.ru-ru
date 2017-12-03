---
title: Contract1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 20dbd0c86f012b6f29b752c4ad9195ce453f78b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="contract"></a><span data-ttu-id="98952-102">Контракт</span><span class="sxs-lookup"><span data-stu-id="98952-102">Contract</span></span>
<span data-ttu-id="98952-103">Контракт</span><span class="sxs-lookup"><span data-stu-id="98952-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98952-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98952-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="98952-105">Методы</span><span class="sxs-lookup"><span data-stu-id="98952-105">Methods</span></span>  
 <span data-ttu-id="98952-106">Класс контракта не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="98952-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="98952-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="98952-107">Properties</span></span>  
 <span data-ttu-id="98952-108">Класс контракта имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="98952-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="98952-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="98952-109">AppDomainId</span></span>  
 <span data-ttu-id="98952-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="98952-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="98952-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="98952-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="98952-112">Идентификатор домена приложения, который размещает контракт.</span><span class="sxs-lookup"><span data-stu-id="98952-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="98952-113">Расширения функциональности</span><span class="sxs-lookup"><span data-stu-id="98952-113">Behaviors</span></span>  
 <span data-ttu-id="98952-114">Тип данных: массив Behavior</span><span class="sxs-lookup"><span data-stu-id="98952-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="98952-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="98952-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="98952-116">Поведения, связанные с этим контрактом.</span><span class="sxs-lookup"><span data-stu-id="98952-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="98952-117">Имя</span><span class="sxs-lookup"><span data-stu-id="98952-117">Name</span></span>  
 <span data-ttu-id="98952-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="98952-118">Data type: string</span></span>  
  
 <span data-ttu-id="98952-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="98952-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="98952-120">Имя контракта в WSDL.</span><span class="sxs-lookup"><span data-stu-id="98952-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="98952-121">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="98952-121">Namespace</span></span>  
 <span data-ttu-id="98952-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="98952-122">Data type: string</span></span>  
  
 <span data-ttu-id="98952-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="98952-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="98952-124">Пространство имен элемента `portType` в WSDL.</span><span class="sxs-lookup"><span data-stu-id="98952-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="98952-125">Операции</span><span class="sxs-lookup"><span data-stu-id="98952-125">Operations</span></span>  
 <span data-ttu-id="98952-126">Тип данных: массив Operation</span><span class="sxs-lookup"><span data-stu-id="98952-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="98952-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="98952-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="98952-128">Операции данного контракта.</span><span class="sxs-lookup"><span data-stu-id="98952-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="98952-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="98952-129">ProcessId</span></span>  
 <span data-ttu-id="98952-130">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="98952-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="98952-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="98952-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="98952-132">Идентификатор процесса, который размещает контракт.</span><span class="sxs-lookup"><span data-stu-id="98952-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="98952-133">ref</span><span class="sxs-lookup"><span data-stu-id="98952-133">ref</span></span>  
 <span data-ttu-id="98952-134">Тип данных: Contract</span><span class="sxs-lookup"><span data-stu-id="98952-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="98952-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="98952-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="98952-136">Тип обратного вызова, когда контракт является дуплексным.</span><span class="sxs-lookup"><span data-stu-id="98952-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="98952-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="98952-137">SessionMode</span></span>  
 <span data-ttu-id="98952-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="98952-138">Data type: string</span></span>  
  
 <span data-ttu-id="98952-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="98952-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="98952-140">Указывает, требуется ли для контракта, чтобы связанная с ним привязка использовала сеансы канала.</span><span class="sxs-lookup"><span data-stu-id="98952-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="98952-141">Тип</span><span class="sxs-lookup"><span data-stu-id="98952-141">Type</span></span>  
 <span data-ttu-id="98952-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="98952-142">Data type: string</span></span>  
  
 <span data-ttu-id="98952-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="98952-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="98952-144">Тип контракта.</span><span class="sxs-lookup"><span data-stu-id="98952-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98952-145">Требования</span><span class="sxs-lookup"><span data-stu-id="98952-145">Requirements</span></span>  
  
|<span data-ttu-id="98952-146">MOF</span><span class="sxs-lookup"><span data-stu-id="98952-146">MOF</span></span>|<span data-ttu-id="98952-147">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="98952-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="98952-148">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="98952-148">Namespace</span></span>|<span data-ttu-id="98952-149">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="98952-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="98952-150">См. также</span><span class="sxs-lookup"><span data-stu-id="98952-150">See Also</span></span>  
 <xref:System.ServiceModel.Description.ContractDescription>
