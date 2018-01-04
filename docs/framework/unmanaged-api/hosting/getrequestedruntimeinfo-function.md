---
title: "Функция GetRequestedRuntimeInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeInfo
helpviewer_keywords: GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 49459001d3764988eff7b7a4381a843c44e596cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="getrequestedruntimeinfo-function"></a>Функция GetRequestedRuntimeInfo
Получает сведения о версии и каталоге о общеязыковой среды выполнения (CLR), запрошенный приложением.  
  
 Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `pExe`  
 [in] Имя приложения.  
  
 `pwszVersion`  
 [in] Строка, задающая номер версии среды выполнения.  
  
 `pConfigurationFile`  
 [in] Имя файла конфигурации, который связан с `pExe`.  
  
 `startupFlags`  
 [in] Один или несколько [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) значений перечисления.  
  
 `runtimeInfoFlags`  
 [in] Один или несколько [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) значений перечисления.  
  
 `pDirectory`  
 [out] Буфер, содержащий путь к каталогу для выполнения после успешного завершения.  
  
 `dwDirectory`  
 [in] Длина буфера каталога.  
  
 `dwDirectoryLength`  
 [out] Указатель на длину строки пути каталога.  
  
 `pVersion`  
 [out] Буфер, содержащий номер версии среды выполнения после успешного завершения.  
  
 `cchBuffer`  
 [in] Длина буфера строки версии.  
  
 `dwlength`  
 [out] Указатель на длину строки версии.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок модели объектов компонентов (COM), как определено в файле WinError.h, кроме следующих значений.  
  
|Код возврата|Описание:|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|ERROR_INSUFFICIENT_BUFFER|Размер буфера каталога недостаточно велик для хранения путь к каталогу.<br /><br /> -или-<br /><br /> Размер буфера версии недостаточен для хранения строки версии.|  
  
## <a name="remarks"></a>Примечания  
 `GetRequestedRuntimeInfo` Метод возвращает во время выполнения сведения о версии, загруженной в процесс, который не обязательно является последней версией, установленной на компьютере.  
  
 В .NET Framework версии 2.0, можно получить сведения о последней установленной версии с помощью `GetRequestedRuntimeInfo` метод следующим образом:  
  
-   Укажите `pExe`, `pwszVersion`, и `pConfigurationFile` параметров как null.  
  
-   Укажите флаг RUNTIME_INFO_UPGRADE_VERSION в `RUNTIME_INFO_FLAGS` перечисления для `runtimeInfoFlags` параметра.  
  
 `GetRequestedRuntimeInfo` Метод не возвращает последнюю версию среды CLR в следующих случаях:  
  
-   Существует файл конфигурации приложения, который указывает, загружает определенную версию среды CLR. Обратите внимание, что платформа .NET Framework используется файл конфигурации, даже если указано значение null для `pConfigurationFile` параметра.  
  
-   [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) был вызван метод, указав более ранней версии CLR.  
  
-   В настоящее время выполняется приложение, скомпилированное для более ранней версии CLR.  
  
 Для `runtimeInfoFlags` параметр, можно указать только один из архитектуры константы `RUNTIME_INFO_FLAGS` перечисления одновременно:  
  
-   RUNTIME_INFO_REQUEST_IA64  
  
-   RUNTIME_INFO_REQUEST_AMD64  
  
-   RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Функция GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [Функция GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
