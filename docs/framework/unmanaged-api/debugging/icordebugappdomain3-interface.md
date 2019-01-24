---
title: Интерфейс ICorDebugAppDomain3
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ade4c88f4431dd6db636ea2581bdb936ac8d8e5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538015"
---
# <a name="icordebugappdomain3-interface"></a>Интерфейс ICorDebugAppDomain3
Предоставляет методы для получения сведений об управляемых представлений [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов, в настоящий момент загружены в домен приложения. Этот интерфейс является расширением ICorDebugAppDomain и ICorDebugAppDomain2 интерфейсов.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|Получает перечислитель для всех кэшированных [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов.|  
|[ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|Получает перечислитель для кэшированных [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов в домене приложения, по их идентификаторам интерфейс.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс предназначен для использования с помощью отладчика в сочетании с вызовом функции оценки `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`. Когда этот метод извлекает идентификаторы интерфейса, поддерживаемых [!INCLUDE[wrt](../../../../includes/wrt-md.md)] объекта сервера, отладчик может использовать методы, определенные в этом интерфейсе, чтобы сопоставить их с управляемых типов, которые соответствуют эти интерфейсы.  
  
 Чтобы получить экземпляр этого интерфейса, выполните `QueryInterface` на экземпляр интерфейса ICorDebugAppDomain или ICorDebugAppDomain2.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
