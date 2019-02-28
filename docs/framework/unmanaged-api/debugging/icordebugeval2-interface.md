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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4315c9f5296e8c3ffc9d8241b929c71c2448db6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965869"
---
# <a name="icordebugeval2-interface"></a>Интерфейс ICorDebugEval2

Расширяет «ICorDebugEval» для предоставления поддержки универсальных типов.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|Задает вызов указанного «ICorDebugFunction», который может быть вложен в тип, конструктор которого принимает параметр типа, или можно использовать параметры типа.|  
|[Метод CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|Возвращает указатель на новый «ICorDebugValue» указанного типа, с начальным значением null или нуль.|  
|[Метод NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|Выделяет новый массив элементов указанного типа и измерений.|  
|[Метод NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|Создает новый объект параметризованного типа и вызывает метод-конструктор объекта.|  
|[Метод NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|Создает новый объект параметризованного типа указанного класса не пытается вызвать метод-конструктор|  
|[Метод NewStringWithLength](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|Создает новую строку указанной длины с указанным содержимым.|  
|[Метод RudeAbort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|Прерывает вычисление, `ICorDebugEval2` выполняет.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
