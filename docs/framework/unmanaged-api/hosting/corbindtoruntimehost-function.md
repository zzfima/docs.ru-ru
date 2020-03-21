---
title: Функция CorBindToRuntimeHost
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeHost
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeHost
helpviewer_keywords:
- CorBindToRuntimeHost function [.NET Framework hosting]
ms.assetid: 5c826ba3-8258-49bc-a417-78807915fcaf
topic_type:
- apiref
ms.openlocfilehash: 6566adc442034763e0209869404b60b5afa63866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176491"
---
# <a name="corbindtoruntimehost-function"></a>Функция CorBindToRuntimeHost
Позволяет хостам загружать определенную версию общего времени выполнения языка (CLR) в процесс.  
  
 Эта функция была унесена в системе .NET 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CorBindToRuntimeHost (  
    [in] LPCWSTR       pwszVersion,
    [in] LPCWSTR       pwszBuildFlavor,
    [in] LPCWSTR       pwszHostConfigFile,
    [in] VOID*         pReserved,
    [in] DWORD         startupFlags,
    [in] REFCLSID      rclsid,
    [in] REFIID        riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwszVersion`  
 (в) Строка, описывающая версию CLR, которую вы хотите загрузить.  
  
 Номер версии в рамочном варианте .NET состоит из четырех частей, разделенных периодами: *major.minor.build.revision*. Строка прошла `pwszVersion` так, как должна начаться с символа "v", за которым следуют первые три части номера версии (например, "v1.0.1529").  
  
 Некоторые версии CLR установлены с программным заявлением, которое определяет совместимость с предыдущими версиями CLR. По умолчанию shim запуска `pwszVersion` оценивается в соответствии с политическими заявлениями и загружает последнюю версию времени выполнения, совместимую с запрашиваемым вариантом. Хост может заставить shim пропустить оценку `pwszVersion` политики и загрузить точную версию, указанную в, передавая значение STARTUP_LOADER_SAFEMODE для `startupFlags` параметра.  
  
 `null,` Если `pwszVersion` метод не загружает ни одной версии CLR. Вместо этого он возвращает CLR_E_SHIM_RUNTIMELOAD, что указывает на то, что он не смог загрузить время выполнения.  
  
 `pwszBuildFlavor`  
 (в) Строка, которая определяет, загружать ли сервер или сборку рабочей станции CLR. Допустимые значения: `svr` и `wks`. Сборка сервера оптимизирована, чтобы использовать преимущества нескольких процессоров для сбора мусора, а сборка рабочих станций оптимизирована для клиентских приложений, работающих на однопроцессорной машине.  
  
 Если `pwszBuildFlavor` установка сведена на нет, сборка рабочей станции загружается. При работе на однопроцессорной машине сборка рабочей станции всегда загружается, даже если `pwszBuildFlavor` настроена на. `svr` Однако, `pwszBuildFlavor` если `svr` установлен и одновременное вывоз мусора `startupFlags` указан (см. описание параметра), сборка сервера загружается.  
  
> [!NOTE]
> Параллельный сбор мусора не поддерживается в приложениях под управлением эмулятора WOW64 x86 на 64-битных системах, реализуемых в архитектуре Intel Itanium (ранее именуемой IA-64). Для получения дополнительной информации об использовании WOW64 на 64-битных системах Windows [см.](/windows/desktop/WinProg64/running-32-bit-applications)  
  
 `pwszHostConfigFile`  
 (в) Название файла конфигурации хоста, который определяет версию CLR для загрузки. Если имя файла не включает полностью квалифицированный путь, предполагается, что файл находится в том же каталоге, что и исполняемый, который выполняет вызов.  
  
 `pReserved`  
 (в) Зарезервировано для будущей расширяемости.  
  
 `startupFlags`  
 (в) Набор флагов, который контролирует параллельный сбор мусора, нейтральный код домена и поведение `pwszVersion` параметра. По умолчанию один домен, если флаг не установлен. Список поддерживаемых значений можно узнать [STARTUP_FLAGS.](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)  
  
 `rclsid`  
 (в) Кокласс, `CLSID` который реализует либо [iCorRuntimeHost,](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) либо интерфейс [ICLRRuntimeHost.](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) Поддерживаемые значения являются CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.  
  
 `riid`  
 (в) Интерфейс, `IID` который вы запрашиваете. Поддерживаемые значения IID_ICorRuntimeHost или IID_ICLRRuntimeHost.  
  
 `ppv`  
 (ваут) Указатель интерфейса к версии загруженного времени выполнения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.idl  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Функция CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [Функция CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
