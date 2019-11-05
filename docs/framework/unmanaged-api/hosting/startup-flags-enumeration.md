---
title: Перечисление STARTUP_FLAGS
ms.date: 03/30/2017
api_name:
- STARTUP_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- STARTUP_FLAGS
helpviewer_keywords:
- STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type:
- apiref
ms.openlocfilehash: 1799e0af91fa6074f174120b29e2302a27230c62
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141466"
---
# <a name="startup_flags-enumeration"></a>Перечисление STARTUP_FLAGS
Содержит значения, которые указывают на поведение среды CLR при запуске. По умолчанию сборка мусора не параллельна, и в область, нейтральную к домену, загружается только Библиотека базовых классов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    STARTUP_CONCURRENT_GC                         = 0x1,  
    STARTUP_LOADER_OPTIMIZATION_MASK              = 0x3<<1,  
    STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN     = 0x1<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN      = 0x2<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST = 0x3<<1,  
  
    STARTUP_LOADER_SAFEMODE                       = 0x10,  
    STARTUP_LOADER_SETPREFERENCE                  = 0x100,  
  
    STARTUP_SERVER_GC                             = 0x1000,  
    STARTUP_HOARD_GC_VM                           = 0x2000,  
  
    STARTUP_SINGLE_VERSION_HOSTING_INTERFACE      = 0x4000,  
    STARTUP_LEGACY_IMPERSONATION                  = 0x10000,  
    STARTUP_DISABLE_COMMITTHREADSTACK             = 0x20000,  
    STARTUP_ALWAYSFLOW_IMPERSONATION              = 0x40000,  
    STARTUP_TRIM_GC_COMMIT                        = 0x80000,  
  
    STARTUP_ETW                                   = 0x100000,  
    STARTUP_ARM                                   = 0x400000  
} STARTUP_FLAGS;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|Указывает, что следует использовать параллельную сборку мусора. Если вызывающий объект запрашивает сборку сервера и параллельную сборку мусора на однопроцессорном компьютере, то выполняется сборка рабочей станции и непараллельная сборка мусора. **Примечание.**  Параллельная сборка мусора не поддерживается в приложениях, работающих под управлением эмулятора x86 WOW64 в 64-разрядных системах, которые реализуют архитектуру Intel Itanium (прежнее название — IA-64). Дополнительные сведения об использовании WOW64 в 64-разрядных системах Windows см. в разделе [выполнение 32-разрядных приложений](/windows/desktop/WinProg64/running-32-bit-applications).|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|Указывает, что должна выполняться оптимизация загрузчика.|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|Указывает, что ни одна сборка не загружается как нейтральная к домену.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|Указывает, что все сборки загружаются как нейтральные к домену.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|Указывает, что все сборки со строгими именами загружаются как нейтральные к домену.|  
|`STARTUP_LOADER_SAFEMODE`|Указывает, что политика версий среды CLR не будет применена к переданной версии. Будет загружена точная версия, указанная для CLR. Оболочка совместимости не выполняет оценку политики для определения последней совместимой версии.|  
|`STARTUP_LOADER_SETPREFERENCE`|Указывает, что предпочтительная среда выполнения будет установлена, но фактически не запущена.|  
|`STARTUP_SERVER_GC`|Указывает, что будет использоваться сборка мусора сервера.|  
|`STARTUP_HOARD_GC_VM`|Указывает, что виртуальный адрес будет использоваться при сборке мусора.|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|Указывает, что смешивание интерфейса размещения не будет разрешено.|  
|`STARTUP_LEGACY_IMPERSONATION`|Указывает, что олицетворение не должно проходить через асинхронные точки по умолчанию.|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|Указывает, что весь стек потоков не должен зафиксироваться при запуске потока.|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|Указывает, что управляемые олицетворения и олицетворения, полученные через вызов неуправляемого кода, будут передаваться через асинхронные точки. По умолчанию только управляемые олицетворения будут проходить через асинхронные точки.|  
|`STARTUP_TRIM_GC_COMMIT`|Указывает, что при нехватке системной памяти сборка мусора будет использовать меньше зафиксированного пространства. См. `gcTrimCommitOnLowMemory` в разделе [Оптимизация для размещения общих веб-](../../../standard/garbage-collection/optimization-for-shared-web-hosting.md)сайтов.|  
|`STARTUP_ETW`|Указывает, что трассировка событий для Windows (ETW) включена для событий общеязыковой среды выполнения. Начиная с Windows Vista, трассировка событий всегда включена, поэтому этот флаг не действует. См. раздел [Управление ведением журнала .NET Framework](../../../../docs/framework/performance/controlling-logging.md).|  
|`STARTUP_ARM`|Указывает, что отслеживание ресурсов домена приложения включено. См. свойства <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> и [\<элемент > аппдомаинресаурцемониторинг](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
