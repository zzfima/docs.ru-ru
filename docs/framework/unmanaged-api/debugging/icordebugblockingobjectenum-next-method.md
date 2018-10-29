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
ms.openlocfilehash: 04b28dec0f016d44692665fb0ce95a7e496f103c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200526"
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
  
 Значений входного массива должен быть не меньше размера `celt`. Массив будет заполняться либо следующего `celt` значений в перечислении или всеми оставшимися значениями, если меньше, чем `celt` остаются. При возвращении данного метода `pceltFetched` будет заполняться количество значений, которые были получены. Если `values` содержит недопустимые указатели или указывает на буфер, меньше, чем `celt`, или если `pceltFetched` является недопустимым указателем, результат не определен.  
  
> [!NOTE]
>  Несмотря на то что [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры необходимо освободить, интерфейс «ICorDebugValue» внутри него должны быть сняты.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
