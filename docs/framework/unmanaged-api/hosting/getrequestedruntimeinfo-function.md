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
ms.openlocfilehash: 514c429fd2ec2cda4576245e2656921f0f10f275
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486957"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="76528-102">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="76528-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="76528-103">Возвращает сведения о версии и каталоге об общеязыковой среды выполнения (CLR), запрошенный приложением.</span><span class="sxs-lookup"><span data-stu-id="76528-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="76528-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76528-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76528-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76528-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="76528-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="76528-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="76528-107">[in] Имя приложения.</span><span class="sxs-lookup"><span data-stu-id="76528-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="76528-108">[in] Строка, указывающая номер версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="76528-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="76528-109">[in] Имя файла конфигурации, связанный с `pExe`.</span><span class="sxs-lookup"><span data-stu-id="76528-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="76528-110">[in] Один или несколько из [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="76528-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="76528-111">[in] Один или несколько из [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="76528-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="76528-112">[out] Буфер, содержащий путь к каталогу в среду выполнения, после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="76528-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="76528-113">[in] Длина буфера каталога.</span><span class="sxs-lookup"><span data-stu-id="76528-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="76528-114">[out] Указатель на длину строки пути каталога.</span><span class="sxs-lookup"><span data-stu-id="76528-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="76528-115">[out] Буфер, который содержит номер версии среды выполнения после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="76528-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="76528-116">[in] Длина буфера строки версии.</span><span class="sxs-lookup"><span data-stu-id="76528-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="76528-117">[out] Указатель на длину строки версии.</span><span class="sxs-lookup"><span data-stu-id="76528-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76528-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="76528-118">Return Value</span></span>  
 <span data-ttu-id="76528-119">Этот метод возвращает стандартные коды ошибок объектов модели компонентов (COM), как определено в файле WinError.h, помимо следующих значений.</span><span class="sxs-lookup"><span data-stu-id="76528-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="76528-120">Код возврата</span><span class="sxs-lookup"><span data-stu-id="76528-120">Return code</span></span>|<span data-ttu-id="76528-121">Описание</span><span class="sxs-lookup"><span data-stu-id="76528-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="76528-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="76528-122">S_OK</span></span>|<span data-ttu-id="76528-123">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="76528-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="76528-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="76528-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="76528-125">Размер буфера каталога не достаточно большую для сохранения пути к каталогу.</span><span class="sxs-lookup"><span data-stu-id="76528-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="76528-126">-или-</span><span class="sxs-lookup"><span data-stu-id="76528-126">- or -</span></span><br /><br /> <span data-ttu-id="76528-127">Версии буфера недостаточен для хранения строки версии.</span><span class="sxs-lookup"><span data-stu-id="76528-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76528-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="76528-128">Remarks</span></span>  
 <span data-ttu-id="76528-129">`GetRequestedRuntimeInfo` Метод возвращает во время выполнения сведения о версии, загруженной в процесс, который не обязательно является последней версией, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="76528-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="76528-130">В .NET Framework версии 2.0, можно получить сведения о последней установленной версии с помощью `GetRequestedRuntimeInfo` метод следующим образом:</span><span class="sxs-lookup"><span data-stu-id="76528-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
-   <span data-ttu-id="76528-131">Укажите `pExe`, `pwszVersion`, и `pConfigurationFile` параметры как значения null.</span><span class="sxs-lookup"><span data-stu-id="76528-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
-   <span data-ttu-id="76528-132">Задайте флаг RUNTIME_INFO_UPGRADE_VERSION в `RUNTIME_INFO_FLAGS` перечислений для `runtimeInfoFlags` параметра.</span><span class="sxs-lookup"><span data-stu-id="76528-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="76528-133">`GetRequestedRuntimeInfo` Метод не возвращает последнюю версию среды CLR в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="76528-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
-   <span data-ttu-id="76528-134">Существует файл конфигурации приложения, который указывает, загружает определенную версию среды CLR.</span><span class="sxs-lookup"><span data-stu-id="76528-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="76528-135">Обратите внимание на то, что платформа .NET Framework будет использовать файл конфигурации, даже если указать значение null для `pConfigurationFile` параметра.</span><span class="sxs-lookup"><span data-stu-id="76528-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
-   <span data-ttu-id="76528-136">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) был вызван метод, указав более ранней версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="76528-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
-   <span data-ttu-id="76528-137">Приложение, скомпилированное для более ранней версии среды CLR в данный момент выполняется.</span><span class="sxs-lookup"><span data-stu-id="76528-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="76528-138">Для `runtimeInfoFlags` параметр, можно указать только один из констант архитектура `RUNTIME_INFO_FLAGS` перечисления за раз:</span><span class="sxs-lookup"><span data-stu-id="76528-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
-   <span data-ttu-id="76528-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="76528-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="76528-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="76528-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="76528-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="76528-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76528-142">Требования</span><span class="sxs-lookup"><span data-stu-id="76528-142">Requirements</span></span>  
 <span data-ttu-id="76528-143">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76528-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76528-144">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="76528-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76528-145">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76528-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76528-146">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76528-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76528-147">См. также</span><span class="sxs-lookup"><span data-stu-id="76528-147">See also</span></span>
- [<span data-ttu-id="76528-148">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="76528-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="76528-149">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="76528-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="76528-150">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="76528-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
