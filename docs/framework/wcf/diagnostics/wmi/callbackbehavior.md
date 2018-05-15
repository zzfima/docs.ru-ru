---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: 2755ac4f365536366b41e743110ce494063a5ecc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="callbackbehavior"></a><span data-ttu-id="b25db-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="b25db-102">CallbackBehavior</span></span>
<span data-ttu-id="b25db-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="b25db-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b25db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b25db-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="b25db-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b25db-105">Methods</span></span>  
 <span data-ttu-id="b25db-106">Класс CallbackBehavior не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="b25db-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b25db-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="b25db-107">Properties</span></span>  
 <span data-ttu-id="b25db-108">Класс CallbackBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="b25db-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="b25db-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="b25db-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="b25db-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="b25db-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="b25db-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b25db-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b25db-112">Если сеанс имеет значение true, он автоматически закрывается при закрытии службой дуплексного сеанса.</span><span class="sxs-lookup"><span data-stu-id="b25db-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="b25db-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="b25db-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="b25db-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="b25db-114">Data type: string</span></span>  
<span data-ttu-id="b25db-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b25db-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b25db-116">Указывает, поддерживает служба один поток, несколько потоков или повторные входящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="b25db-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="b25db-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="b25db-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="b25db-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="b25db-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="b25db-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b25db-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b25db-120">Значение, указывающее, требуется ли передать неизвестные данные сериализации по сети.</span><span class="sxs-lookup"><span data-stu-id="b25db-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="b25db-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="b25db-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="b25db-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="b25db-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="b25db-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b25db-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b25db-124">Если это свойство включено, подробная информация об исключениях в обратном вызове прикрепляется к ошибкам, возвращаемым в службу.</span><span class="sxs-lookup"><span data-stu-id="b25db-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="b25db-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="b25db-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="b25db-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="b25db-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="b25db-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b25db-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b25db-128">Максимальное количество элементов, допустимое в сериализованном объекте.</span><span class="sxs-lookup"><span data-stu-id="b25db-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="b25db-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="b25db-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="b25db-130">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="b25db-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="b25db-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b25db-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b25db-132">Указывает, использовать ли текущий контекст синхронизации для выбора потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="b25db-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="b25db-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="b25db-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="b25db-134">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="b25db-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="b25db-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="b25db-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b25db-136">Указывает, кем выполняется принудительная обработка заголовка SOAP MustUnderstand: системой или приложением.</span><span class="sxs-lookup"><span data-stu-id="b25db-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b25db-137">Требования</span><span class="sxs-lookup"><span data-stu-id="b25db-137">Requirements</span></span>  
  
|<span data-ttu-id="b25db-138">MOF</span><span class="sxs-lookup"><span data-stu-id="b25db-138">MOF</span></span>|<span data-ttu-id="b25db-139">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b25db-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b25db-140">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="b25db-140">Namespace</span></span>|<span data-ttu-id="b25db-141">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="b25db-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b25db-142">См. также</span><span class="sxs-lookup"><span data-stu-id="b25db-142">See Also</span></span>  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>
