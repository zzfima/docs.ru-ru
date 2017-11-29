---
title: "Перечисление METAHOST_POLICY_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: METAHOST_POLICY_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: METAHOST_POLICY_FLAGS
helpviewer_keywords: METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8946fdcc7c23e11a3f3d78070532ac0bf72b33b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="metahostpolicyflags-enumeration"></a><span data-ttu-id="5d67b-102">Перечисление METAHOST_POLICY_FLAGS</span><span class="sxs-lookup"><span data-stu-id="5d67b-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="5d67b-103">Предоставляет политики привязки, которые являются общими для большинства сред выполнения.</span><span class="sxs-lookup"><span data-stu-id="5d67b-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="5d67b-104">Это перечисление используется методом [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="5d67b-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d67b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d67b-105">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="5d67b-106">Члены</span><span class="sxs-lookup"><span data-stu-id="5d67b-106">Members</span></span>  
  
|<span data-ttu-id="5d67b-107">Член</span><span class="sxs-lookup"><span data-stu-id="5d67b-107">Member</span></span>|<span data-ttu-id="5d67b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="5d67b-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="5d67b-109">Определяет политику высокой совместимости, которая не учитывает любые общеязыковая среда выполнения (CLR), который загружается текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="5d67b-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="5d67b-110">Вместо этого она рассматривает только установленные среды CLR и предпочтения компонента, как производный от самого файла сборки, объявленного построения для версии или в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5d67b-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="5d67b-111">Применяет политику обновления результат привязки версии, если точное соответствие не найдено, на основе содержимого реестр\\. NETFramework\Policy\Upgrades.</span><span class="sxs-lookup"><span data-stu-id="5d67b-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="5d67b-112">Это действует так же, как [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="5d67b-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="5d67b-113">Результаты привязки возвращаются, как если бы было запущено образа, предоставленного для вызова метода в новом процессе.</span><span class="sxs-lookup"><span data-stu-id="5d67b-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="5d67b-114">В настоящее время `GetRequestedRuntime` игнорирует набор загружаемых сред выполнения и привязывается к набору установленных исполняющих сред.</span><span class="sxs-lookup"><span data-stu-id="5d67b-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="5d67b-115">Этот флаг позволяет основному приложению определить, какие среда выполнения будет привязан EXE-файла при его запуске.</span><span class="sxs-lookup"><span data-stu-id="5d67b-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="5d67b-116">Если откроется диалоговое окно ошибки `GetRequestedRuntime` не удается найти среду выполнения, которая совместима со входными параметрами.</span><span class="sxs-lookup"><span data-stu-id="5d67b-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="5d67b-117">Начиная с версии [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], это диалоговое окно ошибки могут принимать форму Windows функция диалогового окна, запрашивает, нужна ли пользователь включить соответствующую функцию.</span><span class="sxs-lookup"><span data-stu-id="5d67b-117">Beginning with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="5d67b-118">`GetRequestedRuntime`использует в качестве дополнительных входных данных для процесса привязки образ процесса (и все соответствующие файлы конфигурации).</span><span class="sxs-lookup"><span data-stu-id="5d67b-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="5d67b-119">По умолчанию `GetRequestedRuntime` не применяли пути образа процесса (как правило, EXE, который использовался для запуска процесса) при определении среды выполнения для привязки.</span><span class="sxs-lookup"><span data-stu-id="5d67b-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="5d67b-120">`GetRequestedRuntime`необходимо проверить, установлен ли соответствующий SKU при сведения недоступны в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5d67b-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="5d67b-121">Это позволяет приложениям, не имеющих файлы конфигурации для корректного сбоя в SKU меньше, чем по умолчанию установка платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5d67b-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="5d67b-122">По умолчанию `GetRequestedRuntime` не проверяет, установлен ли соответствующий SKU, если атрибут SKU не указан в файле конфигурации `<supportedRuntime />` элемента.</span><span class="sxs-lookup"><span data-stu-id="5d67b-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="5d67b-123">`GetRequestedRuntime`необходимо проверить, установлен ли соответствующий SKU при сведения недоступны в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5d67b-123">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="5d67b-124">Это позволяет приложениям, не имеющих файлы конфигурации для корректного сбоя в SKU меньше, чем по умолчанию установка платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5d67b-124">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="5d67b-125">По умолчанию `GetRequestedRuntime` не проверяет, установлен ли соответствующий SKU, если атрибут SKU не указан в файле конфигурации `<supportedRuntime />` элемента.</span><span class="sxs-lookup"><span data-stu-id="5d67b-125">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="5d67b-126">`GetRequestedRuntime`следует игнорировать SEM_FAILCRITICALERRORS (который устанавливается путем вызова [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) функции) и Показать диалоговое окно ошибки.</span><span class="sxs-lookup"><span data-stu-id="5d67b-126">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) function), and show the error dialog box.</span></span> <span data-ttu-id="5d67b-127">По умолчанию SEM_FAILCRITICALERRORS подавляет диалоговое окно ошибки.</span><span class="sxs-lookup"><span data-stu-id="5d67b-127">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="5d67b-128">Он может быть унаследованы от другого процесса и автоматической ошибки может быть нежелательно в сценарий.</span><span class="sxs-lookup"><span data-stu-id="5d67b-128">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d67b-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d67b-129">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d67b-130">Требования</span><span class="sxs-lookup"><span data-stu-id="5d67b-130">Requirements</span></span>  
 <span data-ttu-id="5d67b-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d67b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d67b-132">**Заголовок:** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="5d67b-132">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="5d67b-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d67b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d67b-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d67b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d67b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="5d67b-135">See Also</span></span>  
 [<span data-ttu-id="5d67b-136">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="5d67b-136">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="5d67b-137">GetRequestedRuntime-метод</span><span class="sxs-lookup"><span data-stu-id="5d67b-137">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
