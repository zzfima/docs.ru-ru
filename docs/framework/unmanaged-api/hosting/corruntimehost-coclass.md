---
title: "Кокласс CorRuntimeHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRuntimeHost
helpviewer_keywords: CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3d7a272aff3a3c7d32042b76d37fdb15c9dcad4d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
  
## <a name="interfaces"></a>Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|[Icorconfiguration-интерфейс](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|Предоставляет методы для настройки общеязыковой среды выполнения (CLR).|  
|[ICorRuntimeHost-интерфейс](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|Предоставляет методы, позволяющие хост для запуска и остановки среда явным образом, для создания и настройки доменов приложений, для доступа к области по умолчанию и перечисления всех доменов, выполняемых в процессе.|  
|[Idebuggerinfo-интерфейс](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|Предоставляет методы для получения сведений о состоянии служб отладки.|  
|[Igchost-интерфейс](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|Предоставляет методы для получения сведений о системе сборки мусора, а также для управления некоторыми аспектами сбора мусора.|  
|«IValidator»|Предоставляет методы для проверки переносимого исполняемого образа и подробные отчеты об ошибках проверки.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.idl  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Размещение компонентных классов](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
