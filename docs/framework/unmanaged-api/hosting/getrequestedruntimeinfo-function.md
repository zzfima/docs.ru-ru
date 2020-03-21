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
ms.openlocfilehash: db721e1ef774c87de0fa7da178463d832a3da756
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178153"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="eb7d8-102">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="eb7d8-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="eb7d8-103">Получает информацию о версии и каталоге о времени выполнения общего языка (CLR), запрошенном приложением.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="eb7d8-104">Эта функция была унесена в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb7d8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb7d8-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="eb7d8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="eb7d8-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="eb7d8-107">(в) Название приложения.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="eb7d8-108">(в) Строка, определяющая номер версии времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="eb7d8-109">(в) Имя файла конфигурации, который `pExe`связан с .</span><span class="sxs-lookup"><span data-stu-id="eb7d8-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="eb7d8-110">(в) Одно или несколько [значений STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="eb7d8-111">(в) Одно или несколько [значений RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="eb7d8-112">(ваут) Буфер, содержащий путь каталога к времени выполнения после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="eb7d8-113">(в) Длина буфера каталога.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="eb7d8-114">(ваут) Указатель на длину строки пути каталога.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="eb7d8-115">(ваут) Буфер, содержащий номер версии времени выполнения после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="eb7d8-116">(в) Длина буфера строки версии.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="eb7d8-117">(ваут) Указатель на длину строки версии.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb7d8-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="eb7d8-118">Return Value</span></span>  
 <span data-ttu-id="eb7d8-119">Этот метод возвращает стандартные коды ошибок компонентной модели объектов (COM), как это определено в WinError.h, в дополнение к следующим значениям.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="eb7d8-120">Код возврата</span><span class="sxs-lookup"><span data-stu-id="eb7d8-120">Return code</span></span>|<span data-ttu-id="eb7d8-121">Описание</span><span class="sxs-lookup"><span data-stu-id="eb7d8-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="eb7d8-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb7d8-122">S_OK</span></span>|<span data-ttu-id="eb7d8-123">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="eb7d8-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="eb7d8-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="eb7d8-125">Буфер каталога недостаточно велик для хранения пути каталога.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="eb7d8-126">— или —</span><span class="sxs-lookup"><span data-stu-id="eb7d8-126">- or -</span></span><br /><br /> <span data-ttu-id="eb7d8-127">Буфер версии недостаточно велик для хранения строки версии.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb7d8-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="eb7d8-128">Remarks</span></span>  
 <span data-ttu-id="eb7d8-129">Метод `GetRequestedRuntimeInfo` возвращает информацию о загрузоченной версии в процесс, которая не обязательно является последней версией, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="eb7d8-130">В версии .NET Framework 2.0 вы можете получить информацию `GetRequestedRuntimeInfo` о последней установленной версии, используя метод следующим образом:</span><span class="sxs-lookup"><span data-stu-id="eb7d8-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="eb7d8-131">`pExe`Укажите, `pwszVersion`что `pConfigurationFile` и параметры являются нулевыми.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="eb7d8-132">Укажите RUNTIME_INFO_UPGRADE_VERSION флага в `RUNTIME_INFO_FLAGS` перечислениях `runtimeInfoFlags` параметра.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="eb7d8-133">Метод `GetRequestedRuntimeInfo` не возвращает последнюю версию CLR в следующих обстоятельствах:</span><span class="sxs-lookup"><span data-stu-id="eb7d8-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="eb7d8-134">Существует файл конфигурации приложения, опознавающий загрузку определенной версии CLR.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="eb7d8-135">Обратите внимание, что в рамке .NET будет `pConfigurationFile` использоваться файл конфигурации, даже если вы укажете нулевую для параметра.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="eb7d8-136">Метод [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) был назван с указанием более ранней версии CLR.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="eb7d8-137">В настоящее время работает приложение, составленное для более ранней версии CLR.</span><span class="sxs-lookup"><span data-stu-id="eb7d8-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="eb7d8-138">Для `runtimeInfoFlags` параметра можно указать только одну из `RUNTIME_INFO_FLAGS` констант архитектуры перечисления одновременно:</span><span class="sxs-lookup"><span data-stu-id="eb7d8-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="eb7d8-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="eb7d8-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="eb7d8-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="eb7d8-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="eb7d8-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="eb7d8-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb7d8-142">Требования</span><span class="sxs-lookup"><span data-stu-id="eb7d8-142">Requirements</span></span>  
 <span data-ttu-id="eb7d8-143">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb7d8-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb7d8-144">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eb7d8-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb7d8-145">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eb7d8-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb7d8-146">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb7d8-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb7d8-147">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eb7d8-147">See also</span></span>

- [<span data-ttu-id="eb7d8-148">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="eb7d8-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="eb7d8-149">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="eb7d8-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="eb7d8-150">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="eb7d8-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
