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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc1d3ffc34cd74d68bf10cb677b68f0a75bb7c67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="startupflags-enumeration"></a>Перечисление STARTUP_FLAGS
Содержит значения, указывающие поведение при запуске среды common language runtime (CLR). По умолчанию сборщик мусора непараллельной и только в библиотеке базовых классов загружаются в область нейтральные к домену.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|Указывает, что следует использовать параллельную сборку мусора. Если вызывающий объект запрашивает построение сервера и параллельная сборка мусора на однопроцессорного компьютера, вместо этого запускаются построение рабочей станции и непараллельная сборка мусора. **Примечание:** параллельная сборка мусора не поддерживается в приложениях, работающих под управлением WOW64 x86 эмулятора на 64-разрядных системах, которые реализуют архитектуру Intel Itanium (прежнее название — IA-64). Дополнительные сведения об использовании WOW64 в 64-разрядных систем Windows см. в разделе [под управлением 32-разрядных приложений](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|Указывает, что этой оптимизации загрузчика.|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|Указывает, что сборки не загружаются как нейтральные к домену.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|Указывает, что все сборки загружаются как нейтральные к домену.|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|Указывает, что все сборки со строгими именами загружаются как нейтральные к домену.|  
|`STARTUP_LOADER_SAFEMODE`|Указывает, что политика версии среды CLR не будет применяться для переданной версии. Указанная версия среды CLR будут загружены. Прокладка не оценивает политику, чтобы определить последнюю совместимую версию.|  
|`STARTUP_LOADER_SETPREFERENCE`|Указывает предпочтительная среда выполнения будет установить, но фактически не запущен.|  
|`STARTUP_SERVER_GC`|Указывает, что сборка мусора сервера будет использоваться.|  
|`STARTUP_HOARD_GC_VM`|Указывает, что сборка мусора будет хранить используемый виртуальный адрес.|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|Указывает, что смешивание интерфейс размещения не разрешаются.|  
|`STARTUP_LEGACY_IMPERSONATION`|Указывает, что олицетворение не должно проходить через асинхронные точки по умолчанию.|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|Указывает, что полный стек потока не должен фиксироваться при запуске потока.|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|Указывает, что управляемые олицетворения и олицетворения, полученные посредством вызова неуправляемого кода будет проходить через асинхронные точки. По умолчанию только управляемые олицетворения будет проходить через асинхронные точки.|  
|`STARTUP_TRIM_GC_COMMIT`|Указывает, что сборка мусора использует меньшая часть фиксированного объема, когда недостаточно системной памяти. В разделе `gcTrimCommitOnLowMemory` в [оптимизации для общих веб-размещения](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).|  
|`STARTUP_ETW`|Включение трассировки событий для Windows (ETW) для событий среды CLR. Начиная с Windows Vista, трассировка событий всегда включена, поэтому этот флаг не оказывает влияния. В разделе [управление ведения журнала .NET Framework](../../../../docs/framework/performance/controlling-logging.md).|  
|`STARTUP_ARM`|Указывает, что включено отслеживание ресурсов домена приложения. В разделе <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> свойство и [ \<appDomainResourceMonitoring > элемент](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
