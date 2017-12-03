---
title: "Конечная точка"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ed3c01f6943ec2958da56777ac0d6223fff66ab0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint"></a><span data-ttu-id="8e7bf-102">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="8e7bf-102">Endpoint</span></span>
<span data-ttu-id="8e7bf-103">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="8e7bf-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e7bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e7bf-104">Syntax</span></span>  
  
```  
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8e7bf-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8e7bf-105">Methods</span></span>  
 <span data-ttu-id="8e7bf-106">Класс Endpoint определяет следующий метод.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="8e7bf-107">Метод</span><span class="sxs-lookup"><span data-stu-id="8e7bf-107">Method</span></span>|<span data-ttu-id="8e7bf-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8e7bf-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e7bf-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="8e7bf-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="8e7bf-110">Извлекает имя экземпляра счетчика производительности операций</span><span class="sxs-lookup"><span data-stu-id="8e7bf-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="8e7bf-111">Свойства</span><span class="sxs-lookup"><span data-stu-id="8e7bf-111">Properties</span></span>  
 <span data-ttu-id="8e7bf-112">Класс Endpoint имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="8e7bf-113">Адрес</span><span class="sxs-lookup"><span data-stu-id="8e7bf-113">Address</span></span>  
 <span data-ttu-id="8e7bf-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8e7bf-114">Data type: string</span></span>  
  
 <span data-ttu-id="8e7bf-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8e7bf-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e7bf-116">Универсальный код ресурса (URI), содержащий адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="8e7bf-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="8e7bf-117">AddressHeaders</span></span>  
 <span data-ttu-id="8e7bf-118">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="8e7bf-118">Data type: string array</span></span>  
  
 <span data-ttu-id="8e7bf-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8e7bf-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e7bf-120">Коллекция заголовков адреса, прикрепленных к этой конечной точке.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="8e7bf-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="8e7bf-121">AddressIdentity</span></span>  
 <span data-ttu-id="8e7bf-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8e7bf-122">Data type: string</span></span>  
  
 <span data-ttu-id="8e7bf-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8e7bf-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e7bf-124">Удостоверение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="8e7bf-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="8e7bf-125">AppDomainId</span></span>  
 <span data-ttu-id="8e7bf-126">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="8e7bf-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="8e7bf-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8e7bf-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e7bf-128">Идентификатор домена приложения, который размещает конечную точку.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="8e7bf-129">Поведения</span><span class="sxs-lookup"><span data-stu-id="8e7bf-129">Behaviors</span></span>  
 <span data-ttu-id="8e7bf-130">Тип данных: массив Behavior</span><span class="sxs-lookup"><span data-stu-id="8e7bf-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="8e7bf-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8e7bf-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e7bf-132">Коллекция поведений, реализуемых этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="8e7bf-133">Привязка</span><span class="sxs-lookup"><span data-stu-id="8e7bf-133">Binding</span></span>  
 <span data-ttu-id="8e7bf-134">Тип данных: Binding</span><span class="sxs-lookup"><span data-stu-id="8e7bf-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="8e7bf-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8e7bf-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e7bf-136">Привязка, используемая этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="8e7bf-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="8e7bf-137">ContractName</span></span>  
 <span data-ttu-id="8e7bf-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8e7bf-138">Data type: string</span></span>  
  
 <span data-ttu-id="8e7bf-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8e7bf-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e7bf-140">Строка, в которой указывается, какой контракт предоставляется этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="8e7bf-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="8e7bf-141">CounterInstanceName</span></span>  
 <span data-ttu-id="8e7bf-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8e7bf-142">Data type: string</span></span>  
  
 <span data-ttu-id="8e7bf-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8e7bf-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e7bf-144">Имя экземпляра счетчиков производительности конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="8e7bf-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="8e7bf-145">ListenUri</span></span>  
 <span data-ttu-id="8e7bf-146">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8e7bf-146">Data type: string</span></span>  
  
 <span data-ttu-id="8e7bf-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8e7bf-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e7bf-148">Универсальный код ресурса (URI), от которого данная конечная точка ожидает передачи данных.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="8e7bf-149">Имя</span><span class="sxs-lookup"><span data-stu-id="8e7bf-149">Name</span></span>  
 <span data-ttu-id="8e7bf-150">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="8e7bf-150">Data type: string</span></span>  
  
 <span data-ttu-id="8e7bf-151">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8e7bf-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e7bf-152">Уникальное имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="8e7bf-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="8e7bf-153">ProcessId</span></span>  
 <span data-ttu-id="8e7bf-154">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="8e7bf-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="8e7bf-155">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8e7bf-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e7bf-156">Возвращает идентификатор процесса, который размещает конечную точку.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="8e7bf-157">ref</span><span class="sxs-lookup"><span data-stu-id="8e7bf-157">ref</span></span>  
 <span data-ttu-id="8e7bf-158">Тип данных: Contract</span><span class="sxs-lookup"><span data-stu-id="8e7bf-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="8e7bf-159">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8e7bf-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e7bf-160">Контракт, предоставляемый этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e7bf-161">Требования</span><span class="sxs-lookup"><span data-stu-id="8e7bf-161">Requirements</span></span>  
  
|<span data-ttu-id="8e7bf-162">MOF</span><span class="sxs-lookup"><span data-stu-id="8e7bf-162">MOF</span></span>|<span data-ttu-id="8e7bf-163">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8e7bf-164">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="8e7bf-164">Namespace</span></span>|<span data-ttu-id="8e7bf-165">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="8e7bf-165">Defined in root\ServiceModel</span></span>|
