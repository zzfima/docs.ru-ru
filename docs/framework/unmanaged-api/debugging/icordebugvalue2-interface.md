---
title: Интерфейс ICorDebugValue2
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: c6f20b0f7927d79ee56b5b6962137d668dc048d1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791116"
---
# <a name="icordebugvalue2-interface"></a>Интерфейс ICorDebugValue2
Расширяет интерфейс "ICorDebugValue" для обеспечения поддержки объектов "ICorDebugType".  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetExactType](icordebugvalue2-getexacttype-method.md)|Возвращает указатель интерфейса на объект `ICorDebugType`, представляющий <xref:System.Type> этого значения.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)

- [Интерфейс ICorDebugValue3](icordebugvalue3-interface.md)
