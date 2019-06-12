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
ms.openlocfilehash: 256fd900fa73948b4ca42ac6b6f21f145effc461
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025893"
---
# <a name="icordebugappdomain3-interface"></a>Интерфейс ICorDebugAppDomain3
Предоставляет методы для получения сведений об управляемых представления типов среды выполнения Windows, загруженные в домен приложения. Этот интерфейс является расширением ICorDebugAppDomain и ICorDebugAppDomain2 интерфейсов.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|Получает перечислитель для всех кэшированных типов среды выполнения Windows.|  
|[ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|Возвращает перечислитель для кэшированных типов среды выполнения Windows в домене приложения, на основе их идентификаторов интерфейса.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс предназначен для использования с помощью отладчика в сочетании с вызовом функции оценки `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`. Когда этот метод извлекает идентификаторы интерфейса, поддерживаемого объектом среды выполнения Windows server, отладчик может использовать методы, определенные в этом интерфейсе для сопоставления их с управляемых типов, которые соответствуют эти интерфейсы.  
  
 Чтобы получить экземпляр этого интерфейса, выполните `QueryInterface` на экземпляр интерфейса ICorDebugAppDomain или ICorDebugAppDomain2.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** Среда выполнения Windows  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
