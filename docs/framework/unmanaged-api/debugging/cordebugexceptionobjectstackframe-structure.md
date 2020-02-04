---
title: Структура CorDebugExceptionObjectStackFrame
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
ms.openlocfilehash: 2845c15d67e287d6efb0cd0a9c940b69de3a1c0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789366"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a>Структура CorDebugExceptionObjectStackFrame
Представляет сведения о кадре стека из объекта исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`pModule`|Указатель на объект ICorDebugModule для текущего кадра.|  
|`ip`|Значение указателя инструкций (EIP/RIP) для текущего кадра.|  
|`methodDef`|Токен метода для текущего кадра.|  
|`isLastForeignExceptionFrame`|Значение, указывающее, является ли кадр последним кадром во внешнем исключении.|  
  
## <a name="remarks"></a>Заметки  
 Вызывающая сторона должна освободить указатель на объект ICorDebugModule, когда он больше не используется.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
