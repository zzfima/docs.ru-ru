---
title: Интерфейс ICorDebugEval2
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
ms.openlocfilehash: e69b32430651edd0222db874e2659bd959f89549
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788708"
---
# <a name="icordebugeval2-interface"></a>Интерфейс ICorDebugEval2

Расширяет "ICorDebugEval" для обеспечения поддержки универсальных типов.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md)|Настраивает вызов указанного "ICorDebugFunction", который может быть вложен в тип, конструктор которого принимает параметры типа или сам может принимать параметры типа.|  
|[Метод CreateValueForType](icordebugeval2-createvaluefortype-method.md)|Возвращает указатель на новый "ICorDebugValue" указанного типа с начальным значением NULL или нулем.|  
|[Метод NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md)|Выделяет новый массив указанного типа элемента и измерений.|  
|[Метод NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md)|Создает новый объект параметризованного типа и вызывает метод конструктора объекта.|  
|[Метод NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|Создает новый объект параметризованного типа указанного класса без попытки вызова метода конструктора|  
|[Метод NewStringWithLength](icordebugeval2-newstringwithlength-method.md)|Создает новую строку указанной длины с указанным содержимым.|  
|[Метод RudeAbort](icordebugeval2-rudeabort-method.md)|Прерывает вычисление, выполняемое в данный момент `ICorDebugEval2`.|  
  
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
