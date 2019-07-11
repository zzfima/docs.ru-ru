---
title: Метод ICLRMetaHost::GetRuntime
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99b87ca1af6c8e88173624f544117eee700fba17
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779770"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="b42c5-102">Метод ICLRMetaHost::GetRuntime</span><span class="sxs-lookup"><span data-stu-id="b42c5-102">ICLRMetaHost::GetRuntime Method</span></span>
<span data-ttu-id="b42c5-103">Получает [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс, используемый для конкретной версии общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="b42c5-103">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="b42c5-104">Этот метод заменяет [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) функция, используемая с [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) флаг.</span><span class="sxs-lookup"><span data-stu-id="b42c5-104">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b42c5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b42c5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b42c5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b42c5-106">Parameters</span></span>  
 `pwzVersion`  
 <span data-ttu-id="b42c5-107">[in] Версия .NET Framework компиляции, хранятся в метаданных, в формате «v*объект*. *B*[. *X*]».</span><span class="sxs-lookup"><span data-stu-id="b42c5-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="b42c5-108">*Объект*, *B*, и *X* — десятичные числа, соответствующие основной номер версии, дополнительный номер версии и номер сборки.</span><span class="sxs-lookup"><span data-stu-id="b42c5-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b42c5-109">Этот параметр должно соответствовать имени каталога для версии платформы .NET Framework, как оно отображается в разделе C:\Windows\Microsoft.NET\Framework или C:\Windows\Microsoft.NET\Framework64.</span><span class="sxs-lookup"><span data-stu-id="b42c5-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="b42c5-110">Пример значения: «v1.0.3705», «v1.1.4322», «v2.0.50727» и «v4.0. *X*«, где *X* зависит от номера установленного построения.</span><span class="sxs-lookup"><span data-stu-id="b42c5-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="b42c5-111">Префикс «v» является обязательным.</span><span class="sxs-lookup"><span data-stu-id="b42c5-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="b42c5-112">[in] Идентификатор требуемого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b42c5-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="b42c5-113">В настоящее время единственным допустимым значением для этого параметра является IID_ICLRRuntimeInfo.</span><span class="sxs-lookup"><span data-stu-id="b42c5-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="b42c5-114">[out] Указатель на [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс, который соответствует нужную среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="b42c5-114">[out] A pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b42c5-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b42c5-115">Return Value</span></span>  
 <span data-ttu-id="b42c5-116">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="b42c5-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b42c5-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b42c5-117">HRESULT</span></span>|<span data-ttu-id="b42c5-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b42c5-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b42c5-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="b42c5-119">S_OK</span></span>|<span data-ttu-id="b42c5-120">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="b42c5-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="b42c5-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b42c5-121">E_POINTER</span></span>|<span data-ttu-id="b42c5-122">`pwzVersion` или `ppRuntime` равно null.</span><span class="sxs-lookup"><span data-stu-id="b42c5-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b42c5-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="b42c5-123">Remarks</span></span>  
 <span data-ttu-id="b42c5-124">Этот метод постоянно взаимодействует с устаревшими интерфейсами, такие как [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) и устаревшими функциями, таких как устаревшие `CorBindTo*` функции (см. в разделе [устаревшей функции среды CLR размещение](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) в .NET Framework 2.0, интерфейс API размещения).</span><span class="sxs-lookup"><span data-stu-id="b42c5-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="b42c5-125">То есть являются видимыми для нового API среды выполнения, загруженные с старый API, и среды выполнения, загруженные с новым API будут видимы для старый API.</span><span class="sxs-lookup"><span data-stu-id="b42c5-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b42c5-126">Требования</span><span class="sxs-lookup"><span data-stu-id="b42c5-126">Requirements</span></span>  
 <span data-ttu-id="b42c5-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b42c5-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b42c5-128">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="b42c5-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b42c5-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b42c5-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b42c5-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b42c5-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b42c5-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b42c5-131">See also</span></span>

- [<span data-ttu-id="b42c5-132">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="b42c5-132">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="b42c5-133">Устаревшие интерфейсы размещения CLR и коклассы</span><span class="sxs-lookup"><span data-stu-id="b42c5-133">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)
- [<span data-ttu-id="b42c5-134">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="b42c5-134">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="b42c5-135">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="b42c5-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="b42c5-136">Размещение</span><span class="sxs-lookup"><span data-stu-id="b42c5-136">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
