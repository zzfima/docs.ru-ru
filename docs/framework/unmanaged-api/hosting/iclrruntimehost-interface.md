---
title: "Интерфейс ICLRRuntimeHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost
helpviewer_keywords: ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type: apiref
caps.latest.revision: "26"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 332db2680ca23f34893a6c50c5311d73838bc1e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="05122-102">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="05122-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="05122-103">Предоставляет функциональные возможности аналогичны [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) интерфейс, предоставляемый в .NET Framework версии 1, со следующими изменениями:</span><span class="sxs-lookup"><span data-stu-id="05122-103">Provides functionality similar to that of the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
-   <span data-ttu-id="05122-104">Добавление [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) метод, чтобы задать интерфейс управления узла.</span><span class="sxs-lookup"><span data-stu-id="05122-104">The addition of the [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
-   <span data-ttu-id="05122-105">Упущение некоторые методы, предоставляемые `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="05122-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05122-106">Методы</span><span class="sxs-lookup"><span data-stu-id="05122-106">Methods</span></span>  
  
|<span data-ttu-id="05122-107">Метод</span><span class="sxs-lookup"><span data-stu-id="05122-107">Method</span></span>|<span data-ttu-id="05122-108">Описание</span><span class="sxs-lookup"><span data-stu-id="05122-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05122-109">ExecuteApplication-метод</span><span class="sxs-lookup"><span data-stu-id="05122-109">ExecuteApplication Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="05122-110">Используется в сценариях развертывания служб на основе манифестов ClickOnce укажите приложение, которое необходимо активировать в новом домене.</span><span class="sxs-lookup"><span data-stu-id="05122-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="05122-111">ExecuteInAppDomain-метод</span><span class="sxs-lookup"><span data-stu-id="05122-111">ExecuteInAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="05122-112">Указывает <xref:System.AppDomain> в которой выполняется указанный управляемый код.</span><span class="sxs-lookup"><span data-stu-id="05122-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="05122-113">Executeindefaultappdomain-метод</span><span class="sxs-lookup"><span data-stu-id="05122-113">ExecuteInDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="05122-114">Вызывает указанный метод заданного типа в заданной сборке.</span><span class="sxs-lookup"><span data-stu-id="05122-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="05122-115">Getclrcontrol-метод</span><span class="sxs-lookup"><span data-stu-id="05122-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="05122-116">Получает указатель интерфейса типа [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , узлы можно использовать для настройки аспектов среды common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="05122-116">Gets an interface pointer of type [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="05122-117">GetCurrentAppDomainId-метод</span><span class="sxs-lookup"><span data-stu-id="05122-117">GetCurrentAppDomainId Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="05122-118">Возвращает числовой идентификатор <xref:System.AppDomain> , выполняемый в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="05122-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="05122-119">SetHostControl-метод</span><span class="sxs-lookup"><span data-stu-id="05122-119">SetHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="05122-120">Задает интерфейс управления узла.</span><span class="sxs-lookup"><span data-stu-id="05122-120">Sets the host control interface.</span></span> <span data-ttu-id="05122-121">Необходимо вызвать `SetHostControl` перед вызовом `Start`.</span><span class="sxs-lookup"><span data-stu-id="05122-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="05122-122">Start-метод</span><span class="sxs-lookup"><span data-stu-id="05122-122">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|<span data-ttu-id="05122-123">Инициализирует среду CLR в процесс.</span><span class="sxs-lookup"><span data-stu-id="05122-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="05122-124">STOP-метод</span><span class="sxs-lookup"><span data-stu-id="05122-124">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|<span data-ttu-id="05122-125">Останавливает выполнение кода средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="05122-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="05122-126">UnloadAppDomain-метод</span><span class="sxs-lookup"><span data-stu-id="05122-126">UnloadAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="05122-127">Выгружает <xref:System.AppDomain> , соответствующий указанный числовой идентификатор.</span><span class="sxs-lookup"><span data-stu-id="05122-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05122-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="05122-128">Remarks</span></span>  
 <span data-ttu-id="05122-129">Начиная с [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], используйте [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) интерфейс для получения указателя на [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс, а затем вызвать [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) метод, чтобы получить указатель на `ICLRRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="05122-129">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="05122-130">В более ранних версиях платформы .NET Framework узел получает указатель на `ICLRRuntimeHost` экземпляр путем вызова [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="05122-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="05122-131">Для предоставления реализации любого из технологий, предоставляемых в .NET Framework версии 2.0, необходимо использовать `ICLRRuntimeHost` вместо `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="05122-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="05122-132">Не вызывайте [запустить](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод перед вызовом метода [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) метода активации приложения на основе манифеста.</span><span class="sxs-lookup"><span data-stu-id="05122-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="05122-133">Если `Start` сначала вызывается метод `ExecuteApplication` вызов метода завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="05122-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05122-134">Требования</span><span class="sxs-lookup"><span data-stu-id="05122-134">Requirements</span></span>  
 <span data-ttu-id="05122-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05122-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05122-136">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="05122-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05122-137">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="05122-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05122-138">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05122-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05122-139">См. также</span><span class="sxs-lookup"><span data-stu-id="05122-139">See Also</span></span>  
 [<span data-ttu-id="05122-140">Corbindtocurrentruntime-функция</span><span class="sxs-lookup"><span data-stu-id="05122-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="05122-141">CorBindToRuntimeEx-функция</span><span class="sxs-lookup"><span data-stu-id="05122-141">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="05122-142">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="05122-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="05122-143">ICorRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="05122-143">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="05122-144">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="05122-144">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="05122-145">Clrruntimehost-компонентный класс</span><span class="sxs-lookup"><span data-stu-id="05122-145">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
