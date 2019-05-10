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
ms.openlocfilehash: da22cbfe06245d915bed6db9cba220fc32b38942
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64627139"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="ef1d9-102">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ef1d9-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="ef1d9-103">Предоставляет функциональные возможности аналогичны [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) интерфейс, предоставляемый в .NET Framework версии 1, со следующими изменениями:</span><span class="sxs-lookup"><span data-stu-id="ef1d9-103">Provides functionality similar to that of the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="ef1d9-104">Добавление [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) метод, позволяющий настраивать интерфейс управления узла.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-104">The addition of the [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="ef1d9-105">Если пропустить некоторые методы, предоставляемые `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ef1d9-106">Методы</span><span class="sxs-lookup"><span data-stu-id="ef1d9-106">Methods</span></span>  
  
|<span data-ttu-id="ef1d9-107">Метод</span><span class="sxs-lookup"><span data-stu-id="ef1d9-107">Method</span></span>|<span data-ttu-id="ef1d9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ef1d9-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ef1d9-109">Метод ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="ef1d9-109">ExecuteApplication Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="ef1d9-110">Используется в сценариях развертывания служб на основе манифестов ClickOnce для указания приложения, которое будет активировать в новом домене.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="ef1d9-111">Метод ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="ef1d9-111">ExecuteInAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="ef1d9-112">Указывает <xref:System.AppDomain> в которой выполняется указанный управляемый код.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="ef1d9-113">Метод ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="ef1d9-113">ExecuteInDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="ef1d9-114">Вызывает указанный метод указанного типа в заданной сборке.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="ef1d9-115">Метод GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="ef1d9-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="ef1d9-116">Получает указатель интерфейса типа [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) , узлы можно использовать для настройки аспектов общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="ef1d9-116">Gets an interface pointer of type [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="ef1d9-117">Метод GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="ef1d9-117">GetCurrentAppDomainId Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="ef1d9-118">Возвращает числовой идентификатор <xref:System.AppDomain> , выполняемый в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="ef1d9-119">Метод SetHostControl</span><span class="sxs-lookup"><span data-stu-id="ef1d9-119">SetHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="ef1d9-120">Задает интерфейс управления узла.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-120">Sets the host control interface.</span></span> <span data-ttu-id="ef1d9-121">Необходимо вызвать `SetHostControl` перед вызовом `Start`.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="ef1d9-122">Метод Start</span><span class="sxs-lookup"><span data-stu-id="ef1d9-122">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|<span data-ttu-id="ef1d9-123">Инициализирует среду CLR в процесс.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="ef1d9-124">Метод Stop</span><span class="sxs-lookup"><span data-stu-id="ef1d9-124">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|<span data-ttu-id="ef1d9-125">Останавливает выполнение кода средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="ef1d9-126">Метод UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="ef1d9-126">UnloadAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="ef1d9-127">Выгружает <xref:System.AppDomain> , соответствующий указанный числовой идентификатор.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef1d9-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef1d9-128">Remarks</span></span>  
 <span data-ttu-id="ef1d9-129">Начиная с [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], использовать [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) интерфейс для получения указателя на [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс, а затем вызвать [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) метод, чтобы получить указатель на `ICLRRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-129">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="ef1d9-130">В более ранних версиях платформы .NET Framework, узел получает указатель на `ICLRRuntimeHost` экземпляра путем вызова [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="ef1d9-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="ef1d9-131">Чтобы предоставить реализации любой из технологий, предоставляемых в .NET Framework версии 2.0, необходимо использовать `ICLRRuntimeHost` вместо `ICorRuntimeHost`.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ef1d9-132">Не вызывайте [запустить](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод перед вызовом [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) метод для активации приложения на основе манифеста.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="ef1d9-133">Если `Start` во-первых, вызывается метод `ExecuteApplication` вызов метода завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ef1d9-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef1d9-134">Требования</span><span class="sxs-lookup"><span data-stu-id="ef1d9-134">Requirements</span></span>  
 <span data-ttu-id="ef1d9-135">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef1d9-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef1d9-136">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ef1d9-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef1d9-137">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef1d9-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef1d9-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef1d9-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef1d9-139">См. также</span><span class="sxs-lookup"><span data-stu-id="ef1d9-139">See also</span></span>

- [<span data-ttu-id="ef1d9-140">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="ef1d9-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="ef1d9-141">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="ef1d9-141">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="ef1d9-142">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="ef1d9-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="ef1d9-143">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ef1d9-143">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="ef1d9-144">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="ef1d9-144">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ef1d9-145">Кокласс CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ef1d9-145">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
