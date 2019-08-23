---
title: Интерфейс ICLRRuntimeHost
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f159c0b57f2087b608fac8cbc9b9c64ceb063a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965995"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="e61fe-102">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e61fe-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="e61fe-103">Предоставляет функциональные возможности, аналогичные интерфейсу [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) , предоставленному в .NET Framework версии 1, со следующими изменениями:</span><span class="sxs-lookup"><span data-stu-id="e61fe-103">Provides functionality similar to that of the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="e61fe-104">Добавление метода [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) для задания интерфейса элемента управления ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="e61fe-104">The addition of the [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="e61fe-105">Пропуск некоторых методов, `ICorRuntimeHost`предоставляемых.</span><span class="sxs-lookup"><span data-stu-id="e61fe-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e61fe-106">Методы</span><span class="sxs-lookup"><span data-stu-id="e61fe-106">Methods</span></span>  
  
|<span data-ttu-id="e61fe-107">Метод</span><span class="sxs-lookup"><span data-stu-id="e61fe-107">Method</span></span>|<span data-ttu-id="e61fe-108">Описание</span><span class="sxs-lookup"><span data-stu-id="e61fe-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e61fe-109">Метод ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="e61fe-109">ExecuteApplication Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="e61fe-110">Используется в сценариях развертывания ClickOnce на основе манифеста для указания приложения, которое должно быть активировано в новом домене.</span><span class="sxs-lookup"><span data-stu-id="e61fe-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="e61fe-111">Метод ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="e61fe-111">ExecuteInAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="e61fe-112">Указывает, <xref:System.AppDomain> в котором следует выполнить указанный управляемый код.</span><span class="sxs-lookup"><span data-stu-id="e61fe-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="e61fe-113">Метод ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="e61fe-113">ExecuteInDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="e61fe-114">Вызывает указанный метод указанного типа в указанной сборке.</span><span class="sxs-lookup"><span data-stu-id="e61fe-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="e61fe-115">Метод GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="e61fe-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="e61fe-116">Возвращает указатель интерфейса типа [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , который может использоваться узлами для настройки аспектов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="e61fe-116">Gets an interface pointer of type [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="e61fe-117">Метод GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="e61fe-117">GetCurrentAppDomainId Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="e61fe-118">Возвращает числовой идентификатор <xref:System.AppDomain> объекта, который выполняется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="e61fe-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="e61fe-119">Метод SetHostControl</span><span class="sxs-lookup"><span data-stu-id="e61fe-119">SetHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="e61fe-120">Задает интерфейс элемента управления ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="e61fe-120">Sets the host control interface.</span></span> <span data-ttu-id="e61fe-121">Перед вызовом `SetHostControl` `Start`необходимо вызвать.</span><span class="sxs-lookup"><span data-stu-id="e61fe-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="e61fe-122">Метод Start</span><span class="sxs-lookup"><span data-stu-id="e61fe-122">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|<span data-ttu-id="e61fe-123">Инициализирует среду CLR в процессе.</span><span class="sxs-lookup"><span data-stu-id="e61fe-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="e61fe-124">Метод Stop</span><span class="sxs-lookup"><span data-stu-id="e61fe-124">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|<span data-ttu-id="e61fe-125">Останавливает выполнение кода средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="e61fe-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="e61fe-126">Метод UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="e61fe-126">UnloadAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="e61fe-127">Выгружает объект <xref:System.AppDomain> , соответствующий указанному числовому идентификатору.</span><span class="sxs-lookup"><span data-stu-id="e61fe-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e61fe-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="e61fe-128">Remarks</span></span>  
 <span data-ttu-id="e61fe-129">Начиная с .NET Framework 4, используйте интерфейс [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) для получения указателя на интерфейс [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) , а затем вызовите метод [ICLRRuntimeInfo::-interface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) , чтобы получить указатель на `ICLRRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="e61fe-129">Starting with the .NET Framework 4, use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="e61fe-130">В более ранних версиях .NET Framework узел получает указатель на `ICLRRuntimeHost` экземпляр, вызывая [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или [корбиндтокуррентрунтиме](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="e61fe-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="e61fe-131">Чтобы реализовать реализации любой из технологий, предоставляемых в .NET Framework версии 2,0, необходимо использовать `ICLRRuntimeHost` `ICorRuntimeHost`вместо.</span><span class="sxs-lookup"><span data-stu-id="e61fe-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e61fe-132">Не вызывайте метод [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) перед вызовом метода [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) для активации приложения на основе манифеста.</span><span class="sxs-lookup"><span data-stu-id="e61fe-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="e61fe-133">Если метод вызывается первым, вызов `ExecuteApplication` метода завершится ошибкой. `Start`</span><span class="sxs-lookup"><span data-stu-id="e61fe-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e61fe-134">Требования</span><span class="sxs-lookup"><span data-stu-id="e61fe-134">Requirements</span></span>  
 <span data-ttu-id="e61fe-135">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e61fe-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e61fe-136">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e61fe-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e61fe-137">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e61fe-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e61fe-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e61fe-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e61fe-139">См. также</span><span class="sxs-lookup"><span data-stu-id="e61fe-139">See also</span></span>

- [<span data-ttu-id="e61fe-140">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="e61fe-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="e61fe-141">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="e61fe-141">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="e61fe-142">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="e61fe-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="e61fe-143">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e61fe-143">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="e61fe-144">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e61fe-144">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="e61fe-145">Кокласс CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e61fe-145">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
