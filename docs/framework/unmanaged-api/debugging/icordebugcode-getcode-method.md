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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d09681f97829f88bedf53af229298d5d57d764df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcodegetcode-method"></a>Метод ICorDebugCode::GetCode
Возвращает весь код для заданной функции, отформатированной для дизассемблирования. Этот метод является устаревшим в .NET Framework версии 2.0. Используйте [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) вместо него.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `startOffset`  
 [in] Смещение начала функции.  
  
 `endOffset`  
 [in] Смещение конца функции.  
  
 `cBufferAlloc`  
 [in] Размер `buffer` массива, в которой будет возвращаться код.  
  
 `buffer`  
 [out] Массив, в который будет возвращаться код.  
  
 `pcBufferSize`  
 [out] Число байтов, возвращенных.  
  
## <a name="remarks"></a>Примечания  
 Если код функции поделен на несколько блоков, они объединяются в порядке возрастания смещения машинного кода. Границы инструкций не проверяются.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>См. также  
 [Метод GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 
