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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 942c9544a6ce868c3b6296569d4a16a44281cdba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758319"
---
# <a name="corruntimehost-coclass"></a>Компонентный класс CorRuntimeHost
Предоставляет интерфейсы для управления приложениями, которые выполняются в среде CLR.  
  
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
  
## <a name="interfaces"></a>Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|-----------------|  
|[Интерфейс ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|Предоставляет методы для настройки общеязыковой среды выполнения (CLR).|  
|[Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|Предоставляет методы, позволяющие узел для запуска и остановки среда CLR явным образом, для создания и настройки доменов приложений, для доступа к области по умолчанию и для перечисления всех доменов, выполняемых в процессе.|  
|[Интерфейс IDebuggerInfo](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|Предоставляет методы для получения сведений о состоянии служб отладки.|  
|[Интерфейс IGCHost](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|Предоставляет методы для получения информации о сборщик мусора, а также для управления некоторыми аспектами сбора мусора.|  
|«IValidator»|Предоставляет методы для проверки переносимого исполняемого образа и подробные отчеты об ошибках проверки.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.idl  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение коклассов](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
