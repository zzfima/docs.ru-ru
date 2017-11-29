---
title: "Интерфейс ICLRMetaHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost
helpviewer_keywords: ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type: apiref
caps.latest.revision: "28"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d271a69847e3bd4dc972ed8e697b8cd15f049fb9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahost-interface"></a>Интерфейс ICLRMetaHost
Предоставляет методы, возвращающие определенную версию среды common language runtime (CLR) на основе номера его версии, перечислить все установленные среды CLR, все среды выполнения, которые загружены в указанного процесса, версию среды CLR, используемый для компиляции сборки, выхода из процесса с shutdown чистая среда и запрос привязки устаревшего API.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Enumerateinstalledruntimes-метод](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|Возвращает перечисление, содержащее допустимое [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) указатель на интерфейс для каждой версии среды CLR, установленной на компьютере.|  
|[EnumerateLoadedRuntimes-метод](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|Возвращает перечисление, содержащее допустимое [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) указатель на интерфейс для каждой среды CLR, загружаемой в данный процесс. Этот метод заменяет [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).|  
|[Метод ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|Пытается корректно завершить работу всех загруженных сред выполнения и завершает процесс. Заменяет [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) функции.|  
|[GetRuntime-метод](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|Возвращает [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс, который соответствует определенной версии среды CLR. Этот метод заменяет [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) функция, используемая с [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) флаг.|  
|[Getversionfromfile-метод](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|Получает сборки исходной версии платформы .NET Framework компиляции (хранятся в метаданных), по его пути файла. Этот метод заменяет [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).|  
|[Querylegacyv2runtimebinding-метод](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|Возвращает интерфейс, представляющий среду выполнения, к которому устаревшей политике активации связывается, например с помощью `useLegacyV2RuntimeActivationPolicy` атрибут [ \<запуска > элемент](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) запись файла конфигурации, напрямую используя Устаревшие интерфейсы API активации или вызывая [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) метод.|  
|[Requestruntimeloadednotification-метод](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|Гарантирует обратный вызов указателя функции, указанной при первой загрузке версии среды CLR, но еще не запущена. Этот метод заменяет [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)|  
  
## <a name="remarks"></a>Примечания  
 Единственный способ получить экземпляр этого интерфейса заключается в вызове [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) работать следующим образом:  
  
```  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
