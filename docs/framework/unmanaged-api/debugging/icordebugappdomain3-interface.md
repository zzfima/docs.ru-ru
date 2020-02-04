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
ms.openlocfilehash: 1aaccb37ec61ed1ba6a7e6e1f508704973117cca
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784881"
---
# <a name="icordebugappdomain3-interface"></a>Интерфейс ICorDebugAppDomain3
Предоставляет методы для получения сведений об управляемых представлениях среда выполнения Windows типов, которые в настоящее время загружены в домене приложения. Этот интерфейс является расширением интерфейсов ICorDebugAppDomain и ICorDebugAppDomain2.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[ICorDebugAppDomain3:: GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md)|Возвращает перечислитель для всех кэшированных среда выполнения Windowsных типов.|  
|[ICorDebugAppDomain3:: GetCachedWinRTTypesForIIDs](icordebugappdomain3-getcachedwinrttypesforiids-method.md)|Возвращает перечислитель для кэшированных среда выполнения Windowsных типов в домене приложения на основе их идентификаторов интерфейсов.|  
  
## <a name="remarks"></a>Заметки  
 Этот интерфейс предназначен для использования отладчиком в сочетании с вызовом вычисления функции для `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`. Когда метод получает идентификаторы интерфейса, поддерживаемые объектом среда выполнения Windows Server, отладчик может использовать методы, определенные в этом интерфейсе, чтобы сопоставлять их с управляемыми типами, которые соответствуют этим интерфейсам.  
  
 Чтобы получить экземпляр этого интерфейса, запустите `QueryInterface` на экземпляре интерфейса ICorDebugAppDomain или ICorDebugAppDomain2.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** среда выполнения Windows  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
