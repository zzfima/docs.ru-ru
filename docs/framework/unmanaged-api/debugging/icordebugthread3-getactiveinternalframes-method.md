---
title: Метод ICorDebugThread3::GetActiveInternalFrames
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e264f2361c739536d15fbf31d366db74e107bac2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085107"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>Метод ICorDebugThread3::GetActiveInternalFrames
Возвращает массив из внутренних кадрах ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) объектов) в стеке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a>Параметры  
 `cInternalFrames`  
 [in] Количество внутренних кадрах, ожидаемая в `ppInternalFrames`.  
  
 `pcInternalFrames`  
 [out] Указатель на `ULONG32` , содержащий количество внутренних кадров в стеке.  
  
 `ppInternalFrames`  
 [in, out] Указатель на адрес массив внутренней фреймы в стеке.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|[ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) объект был успешно создан.|  
|E_INVALIDARG|`cInternalFrames` не равно нулю и `ppInternalFrames` — `null`, или `pcInternalFrames` является `null`.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames` меньше количество внутренних кадрах.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Примечания  
 Внутренние кадры — это структуры данных, помещается в стек средой выполнения для хранения временных данных.  
  
 При первом вызове `GetActiveInternalFrames`, следует задать `cInternalFrames` параметр 0 (ноль) и `ppInternalFrames` параметр значение null. Когда `GetActiveInternalFrames` сначала возвращает `pcInternalFrames` содержит количество внутренних фреймы в стеке.  
  
 `GetActiveInternalFrames` необходимо также вызвать второй раз. Необходимо передать правильное значение (`pcInternalFrames`) в `cInternalFrames` параметра, и задание указателя на массив подходящего размера в `ppInternalFrames`.  
  
 Используйте [ICorDebugStackWalk::GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) метод, чтобы вернуть фактические кадры стека.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
