---
title: CallbackBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5387e197cdf26a393ba23fd5696eb095dfd17a70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="callbackbehavior"></a><span data-ttu-id="70817-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="70817-102">CallbackBehavior</span></span>
<span data-ttu-id="70817-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="70817-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70817-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70817-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="70817-105">Методы</span><span class="sxs-lookup"><span data-stu-id="70817-105">Methods</span></span>  
 <span data-ttu-id="70817-106">Класс CallbackBehavior не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="70817-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="70817-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="70817-107">Properties</span></span>  
 <span data-ttu-id="70817-108">Класс CallbackBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="70817-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="70817-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="70817-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="70817-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="70817-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="70817-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="70817-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70817-112">Если сеанс имеет значение true, он автоматически закрывается при закрытии службой дуплексного сеанса.</span><span class="sxs-lookup"><span data-stu-id="70817-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="70817-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="70817-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="70817-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="70817-114">Data type: string</span></span>  
<span data-ttu-id="70817-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="70817-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70817-116">Указывает, поддерживает служба один поток, несколько потоков или повторные входящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="70817-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="70817-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="70817-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="70817-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="70817-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="70817-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="70817-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70817-120">Значение, указывающее, требуется ли передать неизвестные данные сериализации по сети.</span><span class="sxs-lookup"><span data-stu-id="70817-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="70817-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="70817-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="70817-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="70817-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="70817-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="70817-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70817-124">Если это свойство включено, подробная информация об исключениях в обратном вызове прикрепляется к ошибкам, возвращаемым в службу.</span><span class="sxs-lookup"><span data-stu-id="70817-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="70817-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="70817-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="70817-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="70817-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="70817-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="70817-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70817-128">Максимальное количество элементов, допустимое в сериализованном объекте.</span><span class="sxs-lookup"><span data-stu-id="70817-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="70817-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="70817-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="70817-130">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="70817-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="70817-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="70817-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70817-132">Указывает, использовать ли текущий контекст синхронизации для выбора потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="70817-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="70817-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="70817-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="70817-134">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="70817-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="70817-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="70817-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70817-136">Указывает, кем выполняется принудительная обработка заголовка SOAP MustUnderstand: системой или приложением.</span><span class="sxs-lookup"><span data-stu-id="70817-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70817-137">Требования</span><span class="sxs-lookup"><span data-stu-id="70817-137">Requirements</span></span>  
  
|<span data-ttu-id="70817-138">MOF</span><span class="sxs-lookup"><span data-stu-id="70817-138">MOF</span></span>|<span data-ttu-id="70817-139">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="70817-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="70817-140">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="70817-140">Namespace</span></span>|<span data-ttu-id="70817-141">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="70817-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70817-142">См. также</span><span class="sxs-lookup"><span data-stu-id="70817-142">See Also</span></span>  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>
