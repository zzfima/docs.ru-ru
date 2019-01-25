---
title: Перечисление METAHOST_POLICY_FLAGS
ms.date: 03/30/2017
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be6aaf33331f432d1f3104962fa4e88c68534f03
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729909"
---
# <a name="metahostpolicyflags-enumeration"></a><span data-ttu-id="6ec7c-102">Перечисление METAHOST_POLICY_FLAGS</span><span class="sxs-lookup"><span data-stu-id="6ec7c-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="6ec7c-103">Предоставляет политики привязки, которые являются общими для большинства сред выполнения.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="6ec7c-104">Это перечисление используется с [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ec7c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ec7c-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6ec7c-106">Участники</span><span class="sxs-lookup"><span data-stu-id="6ec7c-106">Members</span></span>  
  
|<span data-ttu-id="6ec7c-107">Член</span><span class="sxs-lookup"><span data-stu-id="6ec7c-107">Member</span></span>|<span data-ttu-id="6ec7c-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="6ec7c-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="6ec7c-109">Определяет политику высокой совместимости, которая не учитывает любые общеязыковая среда выполнения (CLR), загруженные в текущий процесс.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="6ec7c-110">Вместо этого он считает только установленные среды CLR и настройки компонента, как производный от самого файла сборки, объявленного построения для версии или в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="6ec7c-111">Применяет политику обновления к результату bind версии, если точное соответствие не найдено, на основе содержимого HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\Policy\Upgrades.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="6ec7c-112">Это имеет тот же эффект, что [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="6ec7c-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="6ec7c-113">Привязка результаты возвращаются в том случае, как если бы образа, предоставленного в вызов был запущен в новый процесс.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="6ec7c-114">В настоящее время `GetRequestedRuntime` игнорирует набор загружаемых сред выполнения и привязывается к набору установленных сред выполнения.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="6ec7c-115">Этот флаг позволяет основному приложению определить, какая среда выполнения, EXE-файла будет привязан к при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="6ec7c-116">Диалоговое окно ошибки отображается в том случае, если `GetRequestedRuntime` не удается найти среду выполнения, которая совместима с входными параметрами.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="6ec7c-117">Начиная с версии [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], это диалоговое окно ошибки может принимать форму в диалоговом окне Windows функция, которая запрашивает, нужна ли пользователь для включения соответствующей функции.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-117">Beginning with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="6ec7c-118">`GetRequestedRuntime` использует образ процесса (и все соответствующие файлы конфигурации) в качестве дополнительных входных данных для процесса привязки.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="6ec7c-119">По умолчанию `GetRequestedRuntime` переключается на путь к образу процесса (как правило, EXE, который использовался для запуска процесса) при определении среды выполнения для привязки.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="6ec7c-120">`GetRequestedRuntime` необходимо проверить, установлена ли соответствующий номер SKU, если сведения недоступны в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="6ec7c-121">Это позволяет приложениям, у которых нет файлов конфигурации для корректного завершения сбоем в меньшего размера SKU, чем по умолчанию установка платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="6ec7c-122">По умолчанию `GetRequestedRuntime` не проверяет, установлен ли соответствующий номер SKU, если атрибут SKU не указан в файле конфигурации `<supportedRuntime />` элемент.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="6ec7c-123">`GetRequestedRuntime` необходимо проверить, установлена ли соответствующий номер SKU, если сведения недоступны в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-123">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="6ec7c-124">Это позволяет приложениям, у которых нет файлов конфигурации для корректного завершения сбоем в меньшего размера SKU, чем по умолчанию установка платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-124">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="6ec7c-125">По умолчанию `GetRequestedRuntime` не проверяет, установлен ли соответствующий номер SKU, если атрибут SKU не указан в файле конфигурации `<supportedRuntime />` элемент.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-125">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="6ec7c-126">`GetRequestedRuntime` должен игнорировать SEM_FAILCRITICALERRORS (который устанавливается путем вызова [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) функции) и диалоговое окно ошибки.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-126">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) function), and show the error dialog box.</span></span> <span data-ttu-id="6ec7c-127">По умолчанию SEM_FAILCRITICALERRORS подавляет диалоговое окно ошибки.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-127">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="6ec7c-128">Его могут быть унаследованы от другого процесса и автоматической ошибка может быть нежелательно в вашем сценарии.</span><span class="sxs-lookup"><span data-stu-id="6ec7c-128">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ec7c-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="6ec7c-129">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ec7c-130">Требования</span><span class="sxs-lookup"><span data-stu-id="6ec7c-130">Requirements</span></span>  
 <span data-ttu-id="6ec7c-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ec7c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ec7c-132">**Заголовок.** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="6ec7c-132">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="6ec7c-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6ec7c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ec7c-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ec7c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec7c-135">См. также</span><span class="sxs-lookup"><span data-stu-id="6ec7c-135">See also</span></span>
- [<span data-ttu-id="6ec7c-136">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="6ec7c-136">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="6ec7c-137">Метод GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="6ec7c-137">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
