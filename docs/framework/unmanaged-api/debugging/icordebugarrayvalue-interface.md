---
title: Интерфейс ICorDebugArrayValue
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
ms.openlocfilehash: 0944f3379c18cba56ab65fe40a5b94a64d8a8991
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778204"
---
# <a name="icordebugarrayvalue-interface"></a>Интерфейс ICorDebugArrayValue

Подкласс ICorDebugHeapValue, представляющий одномерный или многомерный массив.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetBaseIndicies](icordebugarrayvalue-getbaseindicies-method.md)|Возвращает базовый индекс каждого измерения в массиве.|  
|[Метод GetCount](icordebugarrayvalue-getcount-method.md)|Возвращает общее число элементов в массиве.|  
|[Метод GetDimensions](icordebugarrayvalue-getdimensions-method.md)|Возвращает размеры массива.|  
|[Метод GetElement](icordebugarrayvalue-getelement-method.md)|Возвращает значение, представляющее заданный элемент в массиве.|  
|[Метод GetElementAtPosition](icordebugarrayvalue-getelementatposition-method.md)|Возвращает элемент в заданной позиции, рассматривая массив как одномерный массив с отсчетом от нуля.|  
|[Метод GetElementType](icordebugarrayvalue-getelementtype-method.md)|Возвращает простой тип элементов в массиве.|  
|[Метод GetRank](icordebugarrayvalue-getrank-method.md)|Получает число измерений в массиве.|  
|[Метод HasBaseIndicies](icordebugarrayvalue-hasbaseindicies-method.md)|Определяет, имеет ли массив базовые индексы.|  
  
## <a name="remarks"></a>Заметки  
 `ICorDebugArrayValue` поддерживает одномерные и многомерные массивы.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
