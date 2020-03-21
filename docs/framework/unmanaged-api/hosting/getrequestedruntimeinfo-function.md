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
# <a name="getrequestedruntimeinfo-function"></a>Функция GetRequestedRuntimeInfo
Получает информацию о версии и каталоге о времени выполнения общего языка (CLR), запрошенном приложением.  
  
 Эта функция была унесена в системе .NET 4.  
  
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
 (в) Название приложения.  
  
 `pwszVersion`  
 (в) Строка, определяющая номер версии времени выполнения.  
  
 `pConfigurationFile`  
 (в) Имя файла конфигурации, который `pExe`связан с .  
  
 `startupFlags`  
 (в) Одно или несколько [значений STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) перечисления.  
  
 `runtimeInfoFlags`  
 (в) Одно или несколько [значений RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) перечисления.  
  
 `pDirectory`  
 (ваут) Буфер, содержащий путь каталога к времени выполнения после успешного завершения.  
  
 `dwDirectory`  
 (в) Длина буфера каталога.  
  
 `dwDirectoryLength`  
 (ваут) Указатель на длину строки пути каталога.  
  
 `pVersion`  
 (ваут) Буфер, содержащий номер версии времени выполнения после успешного завершения.  
  
 `cchBuffer`  
 (в) Длина буфера строки версии.  
  
 `dwlength`  
 (ваут) Указатель на длину строки версии.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок компонентной модели объектов (COM), как это определено в WinError.h, в дополнение к следующим значениям.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|ERROR_INSUFFICIENT_BUFFER|Буфер каталога недостаточно велик для хранения пути каталога.<br /><br /> — или —<br /><br /> Буфер версии недостаточно велик для хранения строки версии.|  
  
## <a name="remarks"></a>Remarks  
 Метод `GetRequestedRuntimeInfo` возвращает информацию о загрузоченной версии в процесс, которая не обязательно является последней версией, установленной на компьютере.  
  
 В версии .NET Framework 2.0 вы можете получить информацию `GetRequestedRuntimeInfo` о последней установленной версии, используя метод следующим образом:  
  
- `pExe`Укажите, `pwszVersion`что `pConfigurationFile` и параметры являются нулевыми.  
  
- Укажите RUNTIME_INFO_UPGRADE_VERSION флага в `RUNTIME_INFO_FLAGS` перечислениях `runtimeInfoFlags` параметра.  
  
 Метод `GetRequestedRuntimeInfo` не возвращает последнюю версию CLR в следующих обстоятельствах:  
  
- Существует файл конфигурации приложения, опознавающий загрузку определенной версии CLR. Обратите внимание, что в рамке .NET будет `pConfigurationFile` использоваться файл конфигурации, даже если вы укажете нулевую для параметра.  
  
- Метод [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) был назван с указанием более ранней версии CLR.  
  
- В настоящее время работает приложение, составленное для более ранней версии CLR.  
  
 Для `runtimeInfoFlags` параметра можно указать только одну из `RUNTIME_INFO_FLAGS` констант архитектуры перечисления одновременно:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Функция GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [Функция GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
