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
ms.openlocfilehash: 25cd3e05bc80dd39d2ca558bb4dd5fb77d255f5a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791399"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>Метод ICorDebugThread3::GetActiveInternalFrames
Возвращает массив внутренних кадров (объектов[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) в стеке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp 
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
 окне Число внутренних кадров, ожидаемых в `ppInternalFrames`.  
  
 `pcInternalFrames`  
 заполняет Указатель на `ULONG32`, содержащий количество внутренних кадров в стеке.  
  
 `ppInternalFrames`  
 [вход, выход] Указатель на адрес массива внутренних кадров в стеке.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Объект [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) успешно создан.|  
|E_INVALIDARG|`cInternalFrames` не равен нулю, `ppInternalFrames` `null`, либо `pcInternalFrames` является `null`.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames` меньше, чем число внутренних кадров.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Заметки  
 Внутренние кадры — это структуры данных, помещаемые в стек средой выполнения для хранения временных данных.  
  
 При первом вызове `GetActiveInternalFrames`следует присвоить параметру `cInternalFrames` значение 0 (ноль), а параметру `ppInternalFrames` — значение null. При первом возвращении `GetActiveInternalFrames` `pcInternalFrames` содержит количество внутренних кадров в стеке.  
  
 затем `GetActiveInternalFrames` следует вызвать второй раз. Необходимо передать правильное число (`pcInternalFrames`) в параметре `cInternalFrames` и указать указатель на массив подходящего размера в `ppInternalFrames`.  
  
 Используйте метод [икордебугстакквалк:: noframes](icordebugthread3-getactiveinternalframes-method.md) для возврата фактических кадров стека.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
