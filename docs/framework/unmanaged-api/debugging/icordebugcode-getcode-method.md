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
ms.openlocfilehash: fde76c3b34fcc9f2321f3426d2801b310f681067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178995"
---
# <a name="icordebugcodegetcode-method"></a>Метод ICorDebugCode::GetCode
Получает весь код для указанной функции, отформатированный для разборки. Этот метод был унесена в версии .NET Framework 2.0. Вместо этого используйте [ICorDebugCode2::GetCodeChunks.](icordebugcode2-getcodechunks-method.md)  
  
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
 (в) Смещение начала функции.  
  
 `endOffset`  
 (в) Смещение конца функции.  
  
 `cBufferAlloc`  
 (в) Размер массива, `buffer` в который будет возвращен код.  
  
 `buffer`  
 (ваут) Массив, в который код будет возвращен.  
  
 `pcBufferSize`  
 (ваут) Число байтов вернулось.  
  
## <a name="remarks"></a>Remarks  
 Если код функции был разделен на несколько фрагментов, они скатированы в порядке увеличения родной смещения. Границы инструкций не проверяются.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Рамочные версии .NET:** 1.1, 1.0  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetCodeChunks](icordebugcode2-getcodechunks-method.md)
