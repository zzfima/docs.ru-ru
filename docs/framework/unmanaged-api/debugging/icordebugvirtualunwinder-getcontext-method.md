---
title: Метод ICorDebugVirtualUnwinder::GetContext
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96410466f17bf6b4e8fff235d434f470cabd9249
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugvirtualunwindergetcontext-method"></a>Метод ICorDebugVirtualUnwinder::GetContext
Получает текущий контекст этого средства очистки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `contextFlags`  
 [in] Флаги, указывающие, какие части контекста следует возвращать (определенные в заголовке WinNt.h).  
  
 `cbContextBuf`  
 [in] Количество байтов в `contextBuf`.  
  
 `contextSize`  
 [out] Указатель на число байтов, фактически записанных в `contextBuf`.  
  
 `contextBuf`  
 [out] Байтовый массив, содержащий текущий контекст этого средства очистки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Любое ошибочное значение HRESULT , полученное процессом mscordbi, считается неустранимым и приводит к возврату интерфейсами API ICorDebug значения `CORDBG_E_DATA_TARGET_ERROR`.  
  
## <a name="remarks"></a>Примечания  
 Задайте начальное значение `contextBuf` аргумент буфер контекста, возвращенный при вызове [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) метод.  
  
> [!NOTE]
>  Этот метод доступен только в машинном коде .NET.  
  
 Поскольку очистка может восстановить только подмножество регистров, например только неизменяемые регистры, контекст может не соответствовать в точности состоянию регистра во время фактического вызова метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
