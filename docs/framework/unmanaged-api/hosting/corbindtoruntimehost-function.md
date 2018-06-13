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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c1d83b32402343f3cd2b5403e328698abd6a930
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436219"
---
# <a name="corbindtoruntimehost-function"></a>Функция CorBindToRuntimeHost
Позволяет узлам загружать в процесс заданную версию среды common language runtime (CLR).  
  
 Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `pwszVersion`  
 [in] Строка, описывающая версию среды CLR, которую требуется загрузить.  
  
 Номер версии платформы .NET Framework состоит из четырех частей, разделенных точками: *major.minor.build.revision*. Строка, переданная как `pwszVersion` должно начинаться с символа «v», следуют первые три части номера версии (например, «v1.0.1529»).  
  
 Некоторые версии среды CLR устанавливаются с помощью оператора политики, указывающее, совместимость с предыдущими версиями среды CLR. По умолчанию оболочка загрузки проверяет `pwszVersion` от инструкции политики и загружает последнюю версию среды выполнения, которая совместима со запрашиваемой. Основное приложение может вынудить оболочку пропустить оценку политики и загрузить точное версия, указанная в `pwszVersion` , передавая значение STARTUP_LOADER_SAFEMODE для `startupFlags` параметра.  
  
 Если `pwszVersion` — `null,` метод не загружает все версии среды CLR. Вместо этого он возвращает CLR_E_SHIM_RUNTIMELOAD, который указывает, что не удалось загрузить среду выполнения.  
  
 `pwszBuildFlavor`  
 [in] Строка, указывающая, следует ли загружать сервера или рабочей станции сборки среды CLR. Допустимые значения: `svr` и `wks`. Построение сервера оптимизировано для использования нескольких процессоров для сборки мусора, а построение рабочей станции оптимизировано для клиентских приложений на однопроцессорного компьютера.  
  
 Если `pwszBuildFlavor` имеет значение null, загружается построение рабочей станции. На компьютере одним процессором всегда загружается построение рабочей станции, даже если `pwszBuildFlavor` равно `svr`. Тем не менее если `pwszBuildFlavor` равно `svr` и указывается параллельная сборка мусора (см. в описании `startupFlags` параметра), загружается построение сервера.  
  
> [!NOTE]
>  Параллельная сборка мусора не поддерживается в приложениях, выполняемых WOW64 x86 эмулятора на 64-разрядных системах, которые реализуют архитектуру Intel Itanium (прежнее название — IA-64). Дополнительные сведения об использовании WOW64 в 64-разрядных систем Windows см. в разделе [под управлением 32-разрядных приложений](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).  
  
 `pwszHostConfigFile`  
 [in] Имя файла конфигурации узла, который указывает версию среды CLR для загрузки. Если имя файла не включает полный путь, предполагается, что файл находится в том же каталоге, что исполняемый объект, который выполняет вызов.  
  
 `pReserved`  
 [in] Зарезервировано для будущего расширения.  
  
 `startupFlags`  
 [in] Набор флагов, определяющих параллельная сборка мусора, независимый от домена код и поведение `pwszVersion` параметра. Значение по умолчанию — один домен, если не установлен флаг. Список поддерживаемых значений см. в разделе [STARTUP_FLAGS-перечисление](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).  
  
 `rclsid`  
 [in] `CLSID` Компонентного класса, который реализует или [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейса. Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] `IID` Интерфейса, для которого запрашивается. Поддерживаемыми значениями являются IID_ICorRuntimeHost и IID_ICLRRuntimeHost.  
  
 `ppv`  
 [out] Указатель интерфейса на версию среды выполнения, который был загружен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.idl  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [Функция CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [Функция CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
