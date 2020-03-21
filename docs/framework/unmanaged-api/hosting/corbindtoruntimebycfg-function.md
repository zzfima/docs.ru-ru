---
title: Функция CorBindToRuntimeByCfg
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
ms.openlocfilehash: 4fbc6e7ea531f65a6b1cd0ec93f4847ab8e4fe83
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178246"
---
# <a name="corbindtoruntimebycfg-function"></a>Функция CorBindToRuntimeByCfg
Загружает время выполнения общего языка (CLR) в процесс, используя информацию о версии, которая читается из файла XML.  
  
 Эта функция была унесена в системе .NET 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pCfgStream`  
 (в) Указатель на `IStream` объект, который читает файл XML.  
  
 `reserved`  
 [in] Зарезервирован для будущего использования. Используйте 0 (ноль) в качестве значения.  
  
 `startupFlags`  
 (в) Значение [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) перечисления, которое определяет поведение стартапа CLR.  
  
 `rclsid`  
 (в) Кокласс, `CLSID` который реализует либо [iCorRuntimeHost,](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) либо интерфейс [ICLRRuntimeHost.](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) Поддерживаемые значения являются CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.  
  
 `riid`  
 (в) Либо `IID` или `ICorRuntimeHost` `ICLRRuntimeHost` интерфейс. Поддерживаемые значения IID_ICorRuntimeHost или IID_ICLRRuntimeHost.  
  
 `ppv`  
 (ваут) Указатель на адрес возвращенного интерфейса.  
  
## <a name="remarks"></a>Remarks  
 Формат файла XML моделируется после стандартного файла конфигурации приложения. Для получения дополнительной информации о файлах XML [см.](../../../../docs/framework/configure-apps/file-schema/index.md)  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Функция CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [Функция CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Функция CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
