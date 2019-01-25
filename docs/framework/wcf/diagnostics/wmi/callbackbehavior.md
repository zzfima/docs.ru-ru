---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: 2854671eaabb37066b57d87a7496183c9e5bba4d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562858"
---
# <a name="callbackbehavior"></a><span data-ttu-id="42e4a-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="42e4a-102">CallbackBehavior</span></span>
<span data-ttu-id="42e4a-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="42e4a-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e4a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42e4a-104">Syntax</span></span>  
  
```csharp
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="42e4a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="42e4a-105">Methods</span></span>  
 <span data-ttu-id="42e4a-106">Класс CallbackBehavior не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="42e4a-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="42e4a-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="42e4a-107">Properties</span></span>  
 <span data-ttu-id="42e4a-108">Класс CallbackBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="42e4a-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="42e4a-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="42e4a-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="42e4a-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="42e4a-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="42e4a-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="42e4a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42e4a-112">Если сеанс имеет значение true, он автоматически закрывается при закрытии службой дуплексного сеанса.</span><span class="sxs-lookup"><span data-stu-id="42e4a-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="42e4a-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="42e4a-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="42e4a-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="42e4a-114">Data type: string</span></span>  
<span data-ttu-id="42e4a-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="42e4a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42e4a-116">Указывает, поддерживает служба один поток, несколько потоков или повторные входящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="42e4a-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="42e4a-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="42e4a-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="42e4a-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="42e4a-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="42e4a-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="42e4a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42e4a-120">Значение, указывающее, требуется ли передать неизвестные данные сериализации по сети.</span><span class="sxs-lookup"><span data-stu-id="42e4a-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="42e4a-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="42e4a-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="42e4a-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="42e4a-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="42e4a-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="42e4a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42e4a-124">Если это свойство включено, подробная информация об исключениях в обратном вызове прикрепляется к ошибкам, возвращаемым в службу.</span><span class="sxs-lookup"><span data-stu-id="42e4a-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="42e4a-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="42e4a-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="42e4a-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="42e4a-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="42e4a-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="42e4a-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42e4a-128">Максимальное количество элементов, допустимое в сериализованном объекте.</span><span class="sxs-lookup"><span data-stu-id="42e4a-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="42e4a-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="42e4a-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="42e4a-130">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="42e4a-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="42e4a-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="42e4a-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42e4a-132">Указывает, использовать ли текущий контекст синхронизации для выбора потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="42e4a-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="42e4a-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="42e4a-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="42e4a-134">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="42e4a-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="42e4a-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="42e4a-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42e4a-136">Указывает, кем выполняется принудительная обработка заголовка SOAP MustUnderstand: системой или приложением.</span><span class="sxs-lookup"><span data-stu-id="42e4a-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42e4a-137">Требования</span><span class="sxs-lookup"><span data-stu-id="42e4a-137">Requirements</span></span>  
  
|<span data-ttu-id="42e4a-138">MOF</span><span class="sxs-lookup"><span data-stu-id="42e4a-138">MOF</span></span>|<span data-ttu-id="42e4a-139">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="42e4a-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="42e4a-140">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="42e4a-140">Namespace</span></span>|<span data-ttu-id="42e4a-141">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="42e4a-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42e4a-142">См. также</span><span class="sxs-lookup"><span data-stu-id="42e4a-142">See also</span></span>
- <xref:System.ServiceModel.CallbackBehaviorAttribute>
