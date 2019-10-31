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
ms.openlocfilehash: cd1d9e768698115bee22e35699b044e0c3526d2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136322"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="4e70d-102">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="4e70d-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="4e70d-103">Возвращает сведения о версии и каталоге о среде CLR, запрашиваемой приложением.</span><span class="sxs-lookup"><span data-stu-id="4e70d-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="4e70d-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4e70d-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e70d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e70d-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4e70d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4e70d-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="4e70d-107">окне Имя приложения.</span><span class="sxs-lookup"><span data-stu-id="4e70d-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="4e70d-108">окне Строка, указывающая номер версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4e70d-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="4e70d-109">окне Имя файла конфигурации, связанного с `pExe`.</span><span class="sxs-lookup"><span data-stu-id="4e70d-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="4e70d-110">окне Одно или несколько значений перечисления [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="4e70d-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="4e70d-111">окне Одно или несколько значений перечисления [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="4e70d-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="4e70d-112">заполняет Буфер, содержащий путь к каталогу среды выполнения после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="4e70d-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="4e70d-113">окне Длина буфера каталога.</span><span class="sxs-lookup"><span data-stu-id="4e70d-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="4e70d-114">заполняет Указатель на длину строки пути к каталогу.</span><span class="sxs-lookup"><span data-stu-id="4e70d-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="4e70d-115">заполняет Буфер, содержащий номер версии среды выполнения после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="4e70d-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="4e70d-116">окне Длина буфера строки версии.</span><span class="sxs-lookup"><span data-stu-id="4e70d-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="4e70d-117">заполняет Указатель на длину строки версии.</span><span class="sxs-lookup"><span data-stu-id="4e70d-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e70d-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4e70d-118">Return Value</span></span>  
 <span data-ttu-id="4e70d-119">Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям.</span><span class="sxs-lookup"><span data-stu-id="4e70d-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="4e70d-120">Код возврата</span><span class="sxs-lookup"><span data-stu-id="4e70d-120">Return code</span></span>|<span data-ttu-id="4e70d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="4e70d-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4e70d-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e70d-122">S_OK</span></span>|<span data-ttu-id="4e70d-123">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="4e70d-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="4e70d-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4e70d-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4e70d-125">Буфер каталога недостаточно велик для хранения пути к каталогу.</span><span class="sxs-lookup"><span data-stu-id="4e70d-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="4e70d-126">-или-</span><span class="sxs-lookup"><span data-stu-id="4e70d-126">- or -</span></span><br /><br /> <span data-ttu-id="4e70d-127">Буфер версии недостаточно велик для хранения строки версии.</span><span class="sxs-lookup"><span data-stu-id="4e70d-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e70d-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="4e70d-128">Remarks</span></span>  
 <span data-ttu-id="4e70d-129">Метод `GetRequestedRuntimeInfo` возвращает сведения времени выполнения о версии, загруженной в процесс, что не обязательно является последней версией, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4e70d-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="4e70d-130">В .NET Framework версии 2,0 можно получить сведения о последней установленной версии с помощью метода `GetRequestedRuntimeInfo`, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="4e70d-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="4e70d-131">Укажите `pExe`, `pwszVersion`и `pConfigurationFile` параметров как null.</span><span class="sxs-lookup"><span data-stu-id="4e70d-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="4e70d-132">Укажите флаг RUNTIME_INFO_UPGRADE_VERSION в перечислениях `RUNTIME_INFO_FLAGS` для параметра `runtimeInfoFlags`.</span><span class="sxs-lookup"><span data-stu-id="4e70d-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="4e70d-133">Метод `GetRequestedRuntimeInfo` не возвращает последнюю версию среды CLR в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="4e70d-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="4e70d-134">Существует файл конфигурации приложения, указывающий загрузку определенной версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4e70d-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="4e70d-135">Обратите внимание, что .NET Framework будет использовать файл конфигурации, даже если для параметра `pConfigurationFile` указано значение null.</span><span class="sxs-lookup"><span data-stu-id="4e70d-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="4e70d-136">Метод [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) был вызван с указанием более ранней версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4e70d-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="4e70d-137">В настоящее время выполняется приложение, которое было скомпилировано для более ранней версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4e70d-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="4e70d-138">Для параметра `runtimeInfoFlags` можно одновременно указать только одну из констант архитектуры перечисления `RUNTIME_INFO_FLAGS`:</span><span class="sxs-lookup"><span data-stu-id="4e70d-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="4e70d-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="4e70d-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="4e70d-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="4e70d-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="4e70d-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="4e70d-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e70d-142">Требования</span><span class="sxs-lookup"><span data-stu-id="4e70d-142">Requirements</span></span>  
 <span data-ttu-id="4e70d-143">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e70d-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e70d-144">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4e70d-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e70d-145">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4e70d-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e70d-146">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e70d-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e70d-147">См. также</span><span class="sxs-lookup"><span data-stu-id="4e70d-147">See also</span></span>

- [<span data-ttu-id="4e70d-148">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="4e70d-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="4e70d-149">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="4e70d-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="4e70d-150">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="4e70d-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
