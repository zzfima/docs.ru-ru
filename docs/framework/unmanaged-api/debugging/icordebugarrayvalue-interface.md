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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99bd3e9ae1faec1b71933681fadf4816b4789c98
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952204"
---
# <a name="icordebugarrayvalue-interface"></a>Интерфейс ICorDebugArrayValue

Подкласс ICorDebugHeapValue, представляющий одномерный или многомерный массив.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetBaseIndicies](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|Возвращает базовый индекс каждого измерения в массиве.|  
|[Метод GetCount](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|Возвращает общее число элементов в массиве.|  
|[Метод GetDimensions](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|Возвращает размеры массива.|  
|[Метод GetElement](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|Возвращает значение, представляющее заданный элемент в массиве.|  
|[Метод GetElementAtPosition](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|Возвращает элемент в заданной позиции, рассматривая массив как одномерный массив с отсчетом от нуля.|  
|[Метод GetElementType](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|Возвращает простой тип элементов в массиве.|  
|[Метод GetRank](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|Получает число измерений в массиве.|  
|[Метод HasBaseIndicies](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|Определяет, имеет ли массив базовые индексы.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugArrayValue`поддерживает одномерный и многомерный массивы.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
