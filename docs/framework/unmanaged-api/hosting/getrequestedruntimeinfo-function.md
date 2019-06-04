---
title: Функция GetRequestedRuntimeInfo
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21b96d435bdb0265d31972edbd4038d0b8cd8d2b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490338"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="7c594-102">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="7c594-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="7c594-103">Возвращает сведения о версии и каталоге об общеязыковой среды выполнения (CLR), запрошенный приложением.</span><span class="sxs-lookup"><span data-stu-id="7c594-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="7c594-104">Эта функция является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="7c594-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c594-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c594-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,   
    [in]  LPCWSTR  pwszVersion,   
    [in]  LPCWSTR  pConfigurationFile,   
    [in]  DWORD    startupFlags,   
    [in]  DWORD    runtimeInfoFlags,   
    [out] LPWSTR   pDirectory,   
    [in]  DWORD    dwDirectory,   
    [out] DWORD   *dwDirectoryLength,   
    [out] LPWSTR   pVersion,   
    [in]  DWORD    cchBuffer,   
    [out] DWORD   *dwlength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c594-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c594-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="7c594-107">[in] Имя приложения.</span><span class="sxs-lookup"><span data-stu-id="7c594-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="7c594-108">[in] Строка, указывающая номер версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="7c594-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="7c594-109">[in] Имя файла конфигурации, связанный с `pExe`.</span><span class="sxs-lookup"><span data-stu-id="7c594-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="7c594-110">[in] Один или несколько из [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="7c594-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="7c594-111">[in] Один или несколько из [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="7c594-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="7c594-112">[out] Буфер, содержащий путь к каталогу в среду выполнения, после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="7c594-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="7c594-113">[in] Длина буфера каталога.</span><span class="sxs-lookup"><span data-stu-id="7c594-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="7c594-114">[out] Указатель на длину строки пути каталога.</span><span class="sxs-lookup"><span data-stu-id="7c594-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="7c594-115">[out] Буфер, который содержит номер версии среды выполнения после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="7c594-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="7c594-116">[in] Длина буфера строки версии.</span><span class="sxs-lookup"><span data-stu-id="7c594-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="7c594-117">[out] Указатель на длину строки версии.</span><span class="sxs-lookup"><span data-stu-id="7c594-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c594-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7c594-118">Return Value</span></span>  
 <span data-ttu-id="7c594-119">Этот метод возвращает стандартные коды ошибок объектов модели компонентов (COM), как определено в файле WinError.h, помимо следующих значений.</span><span class="sxs-lookup"><span data-stu-id="7c594-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="7c594-120">Код возврата</span><span class="sxs-lookup"><span data-stu-id="7c594-120">Return code</span></span>|<span data-ttu-id="7c594-121">Описание</span><span class="sxs-lookup"><span data-stu-id="7c594-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="7c594-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c594-122">S_OK</span></span>|<span data-ttu-id="7c594-123">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="7c594-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="7c594-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="7c594-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="7c594-125">Размер буфера каталога не достаточно большую для сохранения пути к каталогу.</span><span class="sxs-lookup"><span data-stu-id="7c594-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="7c594-126">-или-</span><span class="sxs-lookup"><span data-stu-id="7c594-126">- or -</span></span><br /><br /> <span data-ttu-id="7c594-127">Версии буфера недостаточен для хранения строки версии.</span><span class="sxs-lookup"><span data-stu-id="7c594-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c594-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c594-128">Remarks</span></span>  
 <span data-ttu-id="7c594-129">`GetRequestedRuntimeInfo` Метод возвращает во время выполнения сведения о версии, загруженной в процесс, который не обязательно является последней версией, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7c594-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="7c594-130">В .NET Framework версии 2.0, можно получить сведения о последней установленной версии с помощью `GetRequestedRuntimeInfo` метод следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7c594-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="7c594-131">Укажите `pExe`, `pwszVersion`, и `pConfigurationFile` параметры как значения null.</span><span class="sxs-lookup"><span data-stu-id="7c594-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="7c594-132">Задайте флаг RUNTIME_INFO_UPGRADE_VERSION в `RUNTIME_INFO_FLAGS` перечислений для `runtimeInfoFlags` параметра.</span><span class="sxs-lookup"><span data-stu-id="7c594-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="7c594-133">`GetRequestedRuntimeInfo` Метод не возвращает последнюю версию среды CLR в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="7c594-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="7c594-134">Существует файл конфигурации приложения, который указывает, загружает определенную версию среды CLR.</span><span class="sxs-lookup"><span data-stu-id="7c594-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="7c594-135">Обратите внимание на то, что платформа .NET Framework будет использовать файл конфигурации, даже если указать значение null для `pConfigurationFile` параметра.</span><span class="sxs-lookup"><span data-stu-id="7c594-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="7c594-136">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) был вызван метод, указав более ранней версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="7c594-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="7c594-137">Приложение, скомпилированное для более ранней версии среды CLR в данный момент выполняется.</span><span class="sxs-lookup"><span data-stu-id="7c594-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="7c594-138">Для `runtimeInfoFlags` параметр, можно указать только один из констант архитектура `RUNTIME_INFO_FLAGS` перечисления за раз:</span><span class="sxs-lookup"><span data-stu-id="7c594-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="7c594-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="7c594-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="7c594-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="7c594-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="7c594-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="7c594-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c594-142">Требования</span><span class="sxs-lookup"><span data-stu-id="7c594-142">Requirements</span></span>  
 <span data-ttu-id="7c594-143">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c594-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c594-144">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c594-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c594-145">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c594-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c594-146">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c594-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c594-147">См. также</span><span class="sxs-lookup"><span data-stu-id="7c594-147">See also</span></span>

- [<span data-ttu-id="7c594-148">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="7c594-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="7c594-149">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="7c594-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="7c594-150">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="7c594-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
