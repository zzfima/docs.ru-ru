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
ms.openlocfilehash: 1290aa864a3f65e549bc26173dcd23648b8dee90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61627994"
---
# <a name="getrequestedruntimeinfo-function"></a>Функция GetRequestedRuntimeInfo
Возвращает сведения о версии и каталоге об общеязыковой среды выполнения (CLR), запрошенный приложением.  
  
 Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
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
  
## <a name="parameters"></a>Параметры  
 `pExe`  
 [in] Имя приложения.  
  
 `pwszVersion`  
 [in] Строка, указывающая номер версии среды выполнения.  
  
 `pConfigurationFile`  
 [in] Имя файла конфигурации, связанный с `pExe`.  
  
 `startupFlags`  
 [in] Один или несколько из [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) значений перечисления.  
  
 `runtimeInfoFlags`  
 [in] Один или несколько из [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) значений перечисления.  
  
 `pDirectory`  
 [out] Буфер, содержащий путь к каталогу в среду выполнения, после успешного завершения.  
  
 `dwDirectory`  
 [in] Длина буфера каталога.  
  
 `dwDirectoryLength`  
 [out] Указатель на длину строки пути каталога.  
  
 `pVersion`  
 [out] Буфер, который содержит номер версии среды выполнения после успешного завершения.  
  
 `cchBuffer`  
 [in] Длина буфера строки версии.  
  
 `dwlength`  
 [out] Указатель на длину строки версии.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок объектов модели компонентов (COM), как определено в файле WinError.h, помимо следующих значений.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|ERROR_INSUFFICIENT_BUFFER|Размер буфера каталога не достаточно большую для сохранения пути к каталогу.<br /><br /> -или-<br /><br /> Версии буфера недостаточен для хранения строки версии.|  
  
## <a name="remarks"></a>Примечания  
 `GetRequestedRuntimeInfo` Метод возвращает во время выполнения сведения о версии, загруженной в процесс, который не обязательно является последней версией, установленной на компьютере.  
  
 В .NET Framework версии 2.0, можно получить сведения о последней установленной версии с помощью `GetRequestedRuntimeInfo` метод следующим образом:  
  
- Укажите `pExe`, `pwszVersion`, и `pConfigurationFile` параметры как значения null.  
  
- Задайте флаг RUNTIME_INFO_UPGRADE_VERSION в `RUNTIME_INFO_FLAGS` перечислений для `runtimeInfoFlags` параметра.  
  
 `GetRequestedRuntimeInfo` Метод не возвращает последнюю версию среды CLR в следующих случаях:  
  
- Существует файл конфигурации приложения, который указывает, загружает определенную версию среды CLR. Обратите внимание на то, что платформа .NET Framework будет использовать файл конфигурации, даже если указать значение null для `pConfigurationFile` параметра.  
  
- [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) был вызван метод, указав более ранней версии среды CLR.  
  
- Приложение, скомпилированное для более ранней версии среды CLR в данный момент выполняется.  
  
 Для `runtimeInfoFlags` параметр, можно указать только один из констант архитектура `RUNTIME_INFO_FLAGS` перечисления за раз:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [Функция GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
