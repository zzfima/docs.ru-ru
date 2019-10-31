---
title: Компонентный класс CorRuntimeHost
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
ms.openlocfilehash: 512009e053605e2018f1fcbafa422c1a36ddecc1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136911"
---
# <a name="corruntimehost-coclass"></a>Компонентный класс CorRuntimeHost
Предоставляет интерфейсы для управления приложениями, которые выполняются средой CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
|[Интерфейс ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|Предоставляет методы для настройки среды CLR.|  
|[Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|Предоставляет методы, позволяющие основному приложению запускать и прекращать работу среды CLR, создавать и настраивать домены приложений, получать доступ к домену по умолчанию и перечислять все домены, выполняющиеся в процессе.|  
|[Интерфейс IDebuggerInfo](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|Предоставляет методы для получения сведений о состоянии служб отладки.|  
|[Интерфейс IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|Предоставляет методы для получения сведений о системе сборки мусора и для управления некоторыми аспектами сборки мусора.|  
|IValidator|Предоставляет методы для проверки переносимых исполняемых образов и подробных отчетов об ошибках проверки.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. idl  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение коклассов](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
