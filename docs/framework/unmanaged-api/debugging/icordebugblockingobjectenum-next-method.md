---
title: Метод ICorDebugBlockingObjectEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e94e4da0eea06ce9cc0110002b1def9e4dd4989
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939146"
---
# <a name="icordebugblockingobjectenumnext-method"></a>Метод ICorDebugBlockingObjectEnum::Next
Возвращает указанное число объектов [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) из перечисления, начиная с текущей позиции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a>Параметры  
 `celt`  
 окне Число извлекаемых объектов.  
  
 `values`  
 заполняет Массив указателей на объекты [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) .  
  
 `pceltFetched`  
 заполняет Указатель на количество полученных объектов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие специфичные результаты HRESULT.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|S_FALSE|Значение параметра `pceltFetched` не равно `celt`.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод работает, как типичный перечислитель COM.  
  
 Значения входного массива должны иметь размер `celt`не ниже. Массив будет заполнен либо следующими `celt` значениями в перечислении, либо со всеми оставшимися значениями, если они меньше, чем `celt` осталось. При возврате `pceltFetched` из этого метода будет заполнено количество полученных значений. Если `values` содержит недопустимые указатели или указывает на буфер, который `celt`меньше, или `pceltFetched` если является недопустимым указателем, результат не определен.  
  
> [!NOTE]
> Хотя структуру [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) не нужно освобождать, интерфейс "ICorDebugValue" внутри него должен быть освобожден.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
