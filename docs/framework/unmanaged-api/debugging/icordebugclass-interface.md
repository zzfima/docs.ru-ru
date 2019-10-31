---
title: Интерфейс ICorDebugClass
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
ms.openlocfilehash: 5714597b5e5ca2936aad53217ae934684e75585c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125746"
---
# <a name="icordebugclass-interface"></a>Интерфейс ICorDebugClass

Представляет тип, который может быть базовым или сложным (иными словами, пользовательским). Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Возвращает модуль, который определяет этот класс.|  
|[Метод GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|Возвращает значение указанного статического поля.|  
|[Метод GetToken](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|Возвращает `TypeDef` маркера метаданных для этого класса.|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `ICorDebugClass` представляет универсальный тип, экземпляр которого не был создан. Интерфейс ICorDebugType представляет экземпляр универсального типа. Например, `Hashtable<K, V>` будет представлено `ICorDebugClass`, а `Hashtable<Int32, String>` будет представлено `ICorDebugType`.  
  
 Типы, не являющиеся универсальными, представляются как `ICorDebugClass`, так и `ICorDebugType`. Последний интерфейс появился в .NET Framework версии 2,0 для обработки создания экземпляра типа.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
