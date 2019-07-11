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
ms.openlocfilehash: 630e0c20309b6e791991b64ef8d423ff927b70fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767899"
---
# <a name="corbindtoruntimehost-function"></a>Функция CorBindToRuntimeHost
Позволяет основным приложениям загружать указанную версию общеязыковой среды выполнения (CLR) в процесс.  
  
 Эта функция является устаревшим в .NET Framework 4.  
  
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
 [in] Строка, описывающая версию среды CLR, которую нужно загрузить.  
  
 Номер версии в .NET Framework состоит из четырех частей, разделенных точками: *major.minor.build.revision*. Строка, передаваемая как `pwszVersion` должно начинаться с символа «v», следуют первые три части номера версии (например, «v1.0.1529»).  
  
 В некоторых версиях среды CLR, устанавливаются вместе с инструкцию политики, которая указывает совместимости с предыдущими версиями среды CLR. По умолчанию оболочка загрузки оценивает `pwszVersion` от операторов политик и загружает последнюю версию среды выполнения, совместима с запрашиваемой. Основное приложение может вынудить оболочку пропустить оценку политики и загрузить точной версии, указанной в `pwszVersion` , передав значение STARTUP_LOADER_SAFEMODE для `startupFlags` параметра.  
  
 Если `pwszVersion` является `null,` метод не загружает все версии среды CLR. Вместо этого он возвращает CLR_E_SHIM_RUNTIMELOAD, который указывает, что не удалось загрузить среду выполнения.  
  
 `pwszBuildFlavor`  
 [in] Строковое значение, указывающее, следует ли загружать на сервере или рабочей станции сборки среды CLR. Допустимые значения: `svr` и `wks`. Построение сервера оптимизирован так, чтобы воспользоваться преимуществами нескольких процессоров для сборки мусора и построение рабочей станции оптимизировано для клиентских приложений на однопроцессорном компьютере.  
  
 Если `pwszBuildFlavor` имеет значение null, загружается построение рабочей станции. При выполнении на однопроцессорном компьютере всегда загружается построение рабочей станции, даже если `pwszBuildFlavor` присваивается `svr`. Тем не менее если `pwszBuildFlavor` присваивается `svr` и указывается параллельной сборки мусора (см. в описании `startupFlags` параметр), загружается построение сервера.  
  
> [!NOTE]
>  Параллельная сборка мусора не поддерживается в приложениях, выполняемых WOW64 x86 эмулятора на 64-разрядных системах, которые реализуют архитектуру Intel Itanium (прежнее название — IA-64). Дополнительные сведения об использовании WOW64 в 64-разрядных системах Windows, см. в разделе [под управлением 32-разрядных приложений](/windows/desktop/WinProg64/running-32-bit-applications).  
  
 `pwszHostConfigFile`  
 [in] Имя файла конфигурации узла, который указывает версию среды CLR для загрузки. Если имя файла не включает полный путь, предполагается, что файл находится в том же каталоге, что и исполняемый файл, который выполняет вызов.  
  
 `pReserved`  
 [in] Зарезервировано для будущего расширения.  
  
 `startupFlags`  
 [in] Набор флагов, которое управляет параллельной сборки мусора, независимый от домена код и поведение `pwszVersion` параметра. Значение по умолчанию — один домен, если не установлен флаг. Список поддерживаемых значений, см. в разделе [перечисление STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).  
  
 `rclsid`  
 [in] `CLSID` Компонентного класса, реализующий [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейс. Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] `IID` Интерфейса, для которого запрашивается. Поддерживаемые значения: IID_ICorRuntimeHost и IID_ICLRRuntimeHost.  
  
 `ppv`  
 [out] Указатель интерфейса на версию среды выполнения, который был загружен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.idl  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Функция CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [Функция CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
