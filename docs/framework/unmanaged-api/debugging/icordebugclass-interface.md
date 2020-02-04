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
ms.openlocfilehash: 7ac588591222a1abbc7b99ec7e973284c055f95e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784167"
---
# <a name="icordebugclass-interface"></a>Интерфейс ICorDebugClass

Представляет тип, который может быть базовым или сложным (иными словами, пользовательским). Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetModule](icordebugclass-getmodule-method.md)|Возвращает модуль, который определяет этот класс.|  
|[Метод GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md)|Возвращает значение указанного статического поля.|  
|[Метод GetToken](icordebugclass-gettoken-method.md)|Возвращает `TypeDef` маркера метаданных для этого класса.|  
  
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
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
