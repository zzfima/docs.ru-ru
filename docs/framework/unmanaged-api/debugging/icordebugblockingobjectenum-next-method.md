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
ms.openlocfilehash: b4336978825fbf7844b3ceaf179954f28660f08c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409411"
---
# <a name="icordebugblockingobjectenumnext-method"></a>Метод ICorDebugBlockingObjectEnum::Next
Возвращает заданное число [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) объекты из перечисления, начиная с текущей позиции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
#### <a name="parameters"></a>Параметры  
 `celt`  
 [in] Количество объектов для извлечения.  
  
 `values`  
 [out] Массив указателей на [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) объектов.  
  
 `pceltFetched`  
 [out] Указатель на число объектов, которые были получены.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие специфичные результаты HRESULT.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|S_FALSE|Значение параметра `pceltFetched` не равно `celt`.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод работает, как типичный COM-перечислитель.  
  
 Значений входного массива должен быть не меньше размера `celt`. Массив заполняется либо следующего `celt` значений из перечисления, либо всеми оставшимися значениями, если менее `celt` остаются. По возвращении из этого метода `pceltFetched` будет заполняться количество значений, которые были получены. Если `values` содержит недопустимые указатели или указывает на буфер, меньше, чем `celt`, или если `pceltFetched` является недопустимым указателем, результат будет неопределенным.  
  
> [!NOTE]
>  Несмотря на то что [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) необходимо освободить структуры, интерфейса «ICorDebugValue» внутри объекта необходимо освободить.  
  
-  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
