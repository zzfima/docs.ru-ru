---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: 38a38a71db2927d187ccdd93e5e364b0d4955373
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452616"
---
# <a name="callbackbehavior"></a><span data-ttu-id="0557d-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="0557d-102">CallbackBehavior</span></span>
<span data-ttu-id="0557d-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="0557d-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0557d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0557d-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="0557d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="0557d-105">Methods</span></span>  
 <span data-ttu-id="0557d-106">Класс CallbackBehavior не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="0557d-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0557d-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="0557d-107">Properties</span></span>  
 <span data-ttu-id="0557d-108">Класс CallbackBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="0557d-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="0557d-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="0557d-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="0557d-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="0557d-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="0557d-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0557d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0557d-112">Если сеанс имеет значение true, он автоматически закрывается при закрытии службой дуплексного сеанса.</span><span class="sxs-lookup"><span data-stu-id="0557d-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="0557d-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="0557d-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="0557d-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="0557d-114">Data type: string</span></span>  
<span data-ttu-id="0557d-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0557d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0557d-116">Указывает, поддерживает служба один поток, несколько потоков или повторные входящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="0557d-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="0557d-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="0557d-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="0557d-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="0557d-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="0557d-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0557d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0557d-120">Значение, указывающее, требуется ли передать неизвестные данные сериализации по сети.</span><span class="sxs-lookup"><span data-stu-id="0557d-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="0557d-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="0557d-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="0557d-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="0557d-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="0557d-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0557d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0557d-124">Если это свойство включено, подробная информация об исключениях в обратном вызове прикрепляется к ошибкам, возвращаемым в службу.</span><span class="sxs-lookup"><span data-stu-id="0557d-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="0557d-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="0557d-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="0557d-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="0557d-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="0557d-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0557d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0557d-128">Максимальное количество элементов, допустимое в сериализованном объекте.</span><span class="sxs-lookup"><span data-stu-id="0557d-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="0557d-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="0557d-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="0557d-130">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="0557d-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="0557d-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0557d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0557d-132">Указывает, использовать ли текущий контекст синхронизации для выбора потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="0557d-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="0557d-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="0557d-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="0557d-134">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="0557d-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="0557d-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="0557d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0557d-136">Указывает, кем выполняется принудительная обработка заголовка SOAP MustUnderstand: системой или приложением.</span><span class="sxs-lookup"><span data-stu-id="0557d-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0557d-137">Требования</span><span class="sxs-lookup"><span data-stu-id="0557d-137">Requirements</span></span>  
  
|<span data-ttu-id="0557d-138">MOF</span><span class="sxs-lookup"><span data-stu-id="0557d-138">MOF</span></span>|<span data-ttu-id="0557d-139">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0557d-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0557d-140">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="0557d-140">Namespace</span></span>|<span data-ttu-id="0557d-141">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="0557d-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0557d-142">См. также</span><span class="sxs-lookup"><span data-stu-id="0557d-142">See Also</span></span>  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>
