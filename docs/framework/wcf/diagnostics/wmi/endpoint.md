---
title: Конечная точка
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 4562481e8b0b18c0ea0d9df0af3427ffe6419821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963609"
---
# <a name="endpoint"></a><span data-ttu-id="a2e6b-102">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="a2e6b-102">Endpoint</span></span>
<span data-ttu-id="a2e6b-103">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="a2e6b-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2e6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2e6b-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="a2e6b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a2e6b-105">Methods</span></span>  
 <span data-ttu-id="a2e6b-106">Класс Endpoint определяет следующий метод.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="a2e6b-107">Метод</span><span class="sxs-lookup"><span data-stu-id="a2e6b-107">Method</span></span>|<span data-ttu-id="a2e6b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="a2e6b-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2e6b-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="a2e6b-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="a2e6b-110">Извлекает имя экземпляра счетчика производительности операций</span><span class="sxs-lookup"><span data-stu-id="a2e6b-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="a2e6b-111">Свойства</span><span class="sxs-lookup"><span data-stu-id="a2e6b-111">Properties</span></span>  
 <span data-ttu-id="a2e6b-112">Класс Endpoint имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="a2e6b-113">Адрес</span><span class="sxs-lookup"><span data-stu-id="a2e6b-113">Address</span></span>  
 <span data-ttu-id="a2e6b-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="a2e6b-114">Data type: string</span></span>  
  
 <span data-ttu-id="a2e6b-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="a2e6b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2e6b-116">Универсальный код ресурса (URI), содержащий адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="a2e6b-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="a2e6b-117">AddressHeaders</span></span>  
 <span data-ttu-id="a2e6b-118">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="a2e6b-118">Data type: string array</span></span>  
  
 <span data-ttu-id="a2e6b-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="a2e6b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2e6b-120">Коллекция заголовков адреса, прикрепленных к этой конечной точке.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="a2e6b-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="a2e6b-121">AddressIdentity</span></span>  
 <span data-ttu-id="a2e6b-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="a2e6b-122">Data type: string</span></span>  
  
 <span data-ttu-id="a2e6b-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="a2e6b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2e6b-124">Удостоверение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="a2e6b-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="a2e6b-125">AppDomainId</span></span>  
 <span data-ttu-id="a2e6b-126">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="a2e6b-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="a2e6b-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="a2e6b-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2e6b-128">Идентификатор домена приложения, который размещает конечную точку.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="a2e6b-129">поведения</span><span class="sxs-lookup"><span data-stu-id="a2e6b-129">Behaviors</span></span>  
 <span data-ttu-id="a2e6b-130">Тип данных: Массив Behavior</span><span class="sxs-lookup"><span data-stu-id="a2e6b-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="a2e6b-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="a2e6b-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2e6b-132">Коллекция поведений, реализуемых этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="a2e6b-133">Привязка</span><span class="sxs-lookup"><span data-stu-id="a2e6b-133">Binding</span></span>  
 <span data-ttu-id="a2e6b-134">Тип данных: Привязка</span><span class="sxs-lookup"><span data-stu-id="a2e6b-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="a2e6b-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="a2e6b-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2e6b-136">Привязка, используемая этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="a2e6b-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="a2e6b-137">ContractName</span></span>  
 <span data-ttu-id="a2e6b-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="a2e6b-138">Data type: string</span></span>  
  
 <span data-ttu-id="a2e6b-139">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="a2e6b-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2e6b-140">Строка, в которой указывается, какой контракт предоставляется этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="a2e6b-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="a2e6b-141">CounterInstanceName</span></span>  
 <span data-ttu-id="a2e6b-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="a2e6b-142">Data type: string</span></span>  
  
 <span data-ttu-id="a2e6b-143">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="a2e6b-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2e6b-144">Имя экземпляра счетчиков производительности конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="a2e6b-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="a2e6b-145">ListenUri</span></span>  
 <span data-ttu-id="a2e6b-146">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="a2e6b-146">Data type: string</span></span>  
  
 <span data-ttu-id="a2e6b-147">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="a2e6b-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2e6b-148">Универсальный код ресурса (URI), от которого данная конечная точка ожидает передачи данных.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="a2e6b-149">name</span><span class="sxs-lookup"><span data-stu-id="a2e6b-149">Name</span></span>  
 <span data-ttu-id="a2e6b-150">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="a2e6b-150">Data type: string</span></span>  
  
 <span data-ttu-id="a2e6b-151">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="a2e6b-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2e6b-152">Уникальное имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="a2e6b-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="a2e6b-153">ProcessId</span></span>  
 <span data-ttu-id="a2e6b-154">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="a2e6b-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="a2e6b-155">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="a2e6b-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2e6b-156">Возвращает идентификатор процесса, который размещает конечную точку.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="a2e6b-157">ref</span><span class="sxs-lookup"><span data-stu-id="a2e6b-157">ref</span></span>  
 <span data-ttu-id="a2e6b-158">Тип данных: Контракт</span><span class="sxs-lookup"><span data-stu-id="a2e6b-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="a2e6b-159">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="a2e6b-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a2e6b-160">Контракт, предоставляемый этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2e6b-161">Требования</span><span class="sxs-lookup"><span data-stu-id="a2e6b-161">Requirements</span></span>  
  
|<span data-ttu-id="a2e6b-162">MOF</span><span class="sxs-lookup"><span data-stu-id="a2e6b-162">MOF</span></span>|<span data-ttu-id="a2e6b-163">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a2e6b-164">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="a2e6b-164">Namespace</span></span>|<span data-ttu-id="a2e6b-165">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="a2e6b-165">Defined in root\ServiceModel</span></span>|
