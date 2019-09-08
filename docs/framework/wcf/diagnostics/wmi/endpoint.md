---
title: Конечная точка
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 03c401358839671d750985b95b1aada599931aad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795907"
---
# <a name="endpoint"></a><span data-ttu-id="7e06e-102">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="7e06e-102">Endpoint</span></span>
<span data-ttu-id="7e06e-103">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="7e06e-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e06e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e06e-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="7e06e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="7e06e-105">Methods</span></span>  
 <span data-ttu-id="7e06e-106">Класс Endpoint определяет следующий метод.</span><span class="sxs-lookup"><span data-stu-id="7e06e-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="7e06e-107">Метод</span><span class="sxs-lookup"><span data-stu-id="7e06e-107">Method</span></span>|<span data-ttu-id="7e06e-108">Описание</span><span class="sxs-lookup"><span data-stu-id="7e06e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e06e-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="7e06e-109">GetOperationCounterInstanceName</span></span>](getoperationcounterinstancename.md)|<span data-ttu-id="7e06e-110">Извлекает имя экземпляра счетчика производительности операций</span><span class="sxs-lookup"><span data-stu-id="7e06e-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="7e06e-111">Свойства</span><span class="sxs-lookup"><span data-stu-id="7e06e-111">Properties</span></span>  
 <span data-ttu-id="7e06e-112">Класс Endpoint имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="7e06e-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="7e06e-113">Адрес</span><span class="sxs-lookup"><span data-stu-id="7e06e-113">Address</span></span>  
 <span data-ttu-id="7e06e-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="7e06e-114">Data type: string</span></span>  
  
 <span data-ttu-id="7e06e-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="7e06e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e06e-116">Универсальный код ресурса (URI), содержащий адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7e06e-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="7e06e-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="7e06e-117">AddressHeaders</span></span>  
 <span data-ttu-id="7e06e-118">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="7e06e-118">Data type: string array</span></span>  
  
 <span data-ttu-id="7e06e-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="7e06e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e06e-120">Коллекция заголовков адреса, прикрепленных к этой конечной точке.</span><span class="sxs-lookup"><span data-stu-id="7e06e-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="7e06e-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="7e06e-121">AddressIdentity</span></span>  
 <span data-ttu-id="7e06e-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="7e06e-122">Data type: string</span></span>  
  
 <span data-ttu-id="7e06e-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="7e06e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e06e-124">Удостоверение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7e06e-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="7e06e-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="7e06e-125">AppDomainId</span></span>  
 <span data-ttu-id="7e06e-126">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="7e06e-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="7e06e-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="7e06e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e06e-128">Идентификатор домена приложения, который размещает конечную точку.</span><span class="sxs-lookup"><span data-stu-id="7e06e-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="7e06e-129">поведения</span><span class="sxs-lookup"><span data-stu-id="7e06e-129">Behaviors</span></span>  
 <span data-ttu-id="7e06e-130">Тип данных: Массив поведений</span><span class="sxs-lookup"><span data-stu-id="7e06e-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="7e06e-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="7e06e-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e06e-132">Коллекция поведений, реализуемых этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="7e06e-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="7e06e-133">Привязка</span><span class="sxs-lookup"><span data-stu-id="7e06e-133">Binding</span></span>  
 <span data-ttu-id="7e06e-134">Тип данных: Привязка</span><span class="sxs-lookup"><span data-stu-id="7e06e-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="7e06e-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="7e06e-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e06e-136">Привязка, используемая этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="7e06e-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="7e06e-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="7e06e-137">ContractName</span></span>  
 <span data-ttu-id="7e06e-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="7e06e-138">Data type: string</span></span>  
  
 <span data-ttu-id="7e06e-139">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="7e06e-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e06e-140">Строка, в которой указывается, какой контракт предоставляется этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="7e06e-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="7e06e-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="7e06e-141">CounterInstanceName</span></span>  
 <span data-ttu-id="7e06e-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="7e06e-142">Data type: string</span></span>  
  
 <span data-ttu-id="7e06e-143">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="7e06e-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e06e-144">Имя экземпляра счетчиков производительности конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7e06e-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="7e06e-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="7e06e-145">ListenUri</span></span>  
 <span data-ttu-id="7e06e-146">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="7e06e-146">Data type: string</span></span>  
  
 <span data-ttu-id="7e06e-147">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="7e06e-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e06e-148">Универсальный код ресурса (URI), от которого данная конечная точка ожидает передачи данных.</span><span class="sxs-lookup"><span data-stu-id="7e06e-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="7e06e-149">name</span><span class="sxs-lookup"><span data-stu-id="7e06e-149">Name</span></span>  
 <span data-ttu-id="7e06e-150">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="7e06e-150">Data type: string</span></span>  
  
 <span data-ttu-id="7e06e-151">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="7e06e-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e06e-152">Уникальное имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7e06e-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="7e06e-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="7e06e-153">ProcessId</span></span>  
 <span data-ttu-id="7e06e-154">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="7e06e-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="7e06e-155">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="7e06e-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e06e-156">Возвращает идентификатор процесса, который размещает конечную точку.</span><span class="sxs-lookup"><span data-stu-id="7e06e-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="7e06e-157">ref</span><span class="sxs-lookup"><span data-stu-id="7e06e-157">ref</span></span>  
 <span data-ttu-id="7e06e-158">Тип данных: Контракт</span><span class="sxs-lookup"><span data-stu-id="7e06e-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="7e06e-159">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="7e06e-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7e06e-160">Контракт, предоставляемый этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="7e06e-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e06e-161">Требования</span><span class="sxs-lookup"><span data-stu-id="7e06e-161">Requirements</span></span>  
  
|<span data-ttu-id="7e06e-162">MOF</span><span class="sxs-lookup"><span data-stu-id="7e06e-162">MOF</span></span>|<span data-ttu-id="7e06e-163">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7e06e-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7e06e-164">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="7e06e-164">Namespace</span></span>|<span data-ttu-id="7e06e-165">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="7e06e-165">Defined in root\ServiceModel</span></span>|
