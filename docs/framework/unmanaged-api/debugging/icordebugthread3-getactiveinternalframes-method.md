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
ms.openlocfilehash: 680af5afa3ebef5bcaf9e34580e421dcc8093aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178465"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>Метод ICorDebugThread3::GetActiveInternalFrames
Возвращает массив внутренних кадров (объекты[ICorDebugInternalFrame2)](icordebuginternalframe2-interface.md) в стеке.  
  
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
 (в) Количество внутренних кадров, `ppInternalFrames`ожидаемых в .  
  
 `pcInternalFrames`  
 (ваут) Указатель на `ULONG32` a, содержащий количество внутренних кадров в стеке.  
  
 `ppInternalFrames`  
 (в, вне) Указатель на адрес массива внутренних кадров в стеке.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Успешно создан объект [ICorDebugInternalFrame2.](icordebuginternalframe2-interface.md)|  
|E_INVALIDARG|`cInternalFrames`не равен `ppInternalFrames` `null`нулю `pcInternalFrames` `null`и является, или .|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames`меньше, чем количество внутренних кадров.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Remarks  
 Внутренние кадры — это структуры данных, нажатые на стек временем выполнения для хранения временных данных.  
  
 При первом `GetActiveInternalFrames`вызове необходимо `cInternalFrames` установить параметр до `ppInternalFrames` 0 (ноль), а параметр свести на нет. При `GetActiveInternalFrames` первом `pcInternalFrames` возврате содержится количество внутренних кадров в стеке.  
  
 `GetActiveInternalFrames`затем следует назвать во второй раз. Вы должны пройти надлежащее количество ()`pcInternalFrames`в параметре, `cInternalFrames` и указать указатель на соответствующий размер массива в `ppInternalFrames`.  
  
 Используйте метод [ICorDebugStackWalk::GetFrame,](icordebugthread3-getactiveinternalframes-method.md) чтобы вернуть фактические кадры стека.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладки](index.md)
