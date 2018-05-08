---
title: Кокласс CorRuntimeHost
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9b9b8a728932caa085bba1665dc97faf02be8fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="corruntimehost-coclass"></a>Кокласс CorRuntimeHost
Предоставляет интерфейсы для управления приложениями, которые выполняются в среде CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a>интерфейсов,  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|[Интерфейс ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|Предоставляет методы для настройки общеязыковой среды выполнения (CLR).|  
|[Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|Предоставляет методы, позволяющие хост для запуска и остановки среда явным образом, для создания и настройки доменов приложений, для доступа к области по умолчанию и перечисления всех доменов, выполняемых в процессе.|  
|[Интерфейс IDebuggerInfo](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|Предоставляет методы для получения сведений о состоянии служб отладки.|  
|[Интерфейс IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|Предоставляет методы для получения сведений о системе сборки мусора, а также для управления некоторыми аспектами сбора мусора.|  
|«IValidator»|Предоставляет методы для проверки переносимого исполняемого образа и подробные отчеты об ошибках проверки.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.idl  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Размещение коклассов](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
