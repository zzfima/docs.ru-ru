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
# <a name="getrequestedruntimeinfo-function"></a>Функция GetRequestedRuntimeInfo
Возвращает сведения о версии и каталоге о среде CLR, запрашиваемой приложением.  
  
 Эта функция является устаревшей в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="parameters"></a>Параметры  
 `pExe`  
 окне Имя приложения.  
  
 `pwszVersion`  
 окне Строка, указывающая номер версии среды выполнения.  
  
 `pConfigurationFile`  
 окне Имя файла конфигурации, связанного с `pExe`.  
  
 `startupFlags`  
 окне Одно или несколько значений перечисления [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) .  
  
 `runtimeInfoFlags`  
 окне Одно или несколько значений перечисления [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) .  
  
 `pDirectory`  
 заполняет Буфер, содержащий путь к каталогу среды выполнения после успешного завершения.  
  
 `dwDirectory`  
 окне Длина буфера каталога.  
  
 `dwDirectoryLength`  
 заполняет Указатель на длину строки пути к каталогу.  
  
 `pVersion`  
 заполняет Буфер, содержащий номер версии среды выполнения после успешного завершения.  
  
 `cchBuffer`  
 окне Длина буфера строки версии.  
  
 `dwlength`  
 заполняет Указатель на длину строки версии.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|ERROR_INSUFFICIENT_BUFFER|Буфер каталога недостаточно велик для хранения пути к каталогу.<br /><br /> -или-<br /><br /> Буфер версии недостаточно велик для хранения строки версии.|  
  
## <a name="remarks"></a>Заметки  
 Метод `GetRequestedRuntimeInfo` возвращает сведения времени выполнения о версии, загруженной в процесс, что не обязательно является последней версией, установленной на компьютере.  
  
 В .NET Framework версии 2,0 можно получить сведения о последней установленной версии с помощью метода `GetRequestedRuntimeInfo`, как показано ниже.  
  
- Укажите `pExe`, `pwszVersion`и `pConfigurationFile` параметров как null.  
  
- Укажите флаг RUNTIME_INFO_UPGRADE_VERSION в перечислениях `RUNTIME_INFO_FLAGS` для параметра `runtimeInfoFlags`.  
  
 Метод `GetRequestedRuntimeInfo` не возвращает последнюю версию среды CLR в следующих случаях:  
  
- Существует файл конфигурации приложения, указывающий загрузку определенной версии среды CLR. Обратите внимание, что .NET Framework будет использовать файл конфигурации, даже если для параметра `pConfigurationFile` указано значение null.  
  
- Метод [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) был вызван с указанием более ранней версии среды CLR.  
  
- В настоящее время выполняется приложение, которое было скомпилировано для более ранней версии среды CLR.  
  
 Для параметра `runtimeInfoFlags` можно одновременно указать только одну из констант архитектуры перечисления `RUNTIME_INFO_FLAGS`:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [Функция GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
