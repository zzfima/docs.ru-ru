---
title: Метод ICorDebugCode::GetCode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
ms.openlocfilehash: db24228de7e8c98fd97f890b1e408515172299b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125671"
---
# <a name="icordebugcodegetcode-method"></a>Метод ICorDebugCode::GetCode
Возвращает весь код для указанной функции, отформатированный для дизассемблирования. Этот метод не рекомендуется к использованию в .NET Framework версии 2,0. Вместо этого используйте [ICorDebugCode2:: жеткодечункс](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `startOffset`  
 окне Смещение начала функции.  
  
 `endOffset`  
 окне Смещение конца функции.  
  
 `cBufferAlloc`  
 окне Размер массива `buffer`, в который будет возвращен код.  
  
 `buffer`  
 заполняет Массив, в который будет возвращен код.  
  
 `pcBufferSize`  
 заполняет Число возвращаемых байтов.  
  
## <a name="remarks"></a>Заметки  
 Если код функции делится на несколько блоков, они объединяются в порядке возрастания смещения в машинном коде. Границы инструкций не проверяются.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 1,1, 1,0  
  
## <a name="see-also"></a>См. также

- [Метод GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
