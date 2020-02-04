---
title: Интерфейс ICorDebugDataTarget3
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: 04e7b9a064d4a06a06b8a1518f06092ba79a3561
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783491"
---
# <a name="icordebugdatatarget3-interface"></a>Интерфейс ICorDebugDataTarget3
Логически расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) , чтобы предоставить сведения о загруженных модулях.  
  
## <a name="method"></a>Метод  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetLoadedModules](icordebugdatatarget3-getloadedmodules-method.md)|Возвращает список модулей, загруженных на данный момент.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
