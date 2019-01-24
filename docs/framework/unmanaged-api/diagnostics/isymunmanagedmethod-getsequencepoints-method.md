---
title: Метод ISymUnmanagedMethod::GetSequencePoints
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf6528e8fe6a979db26ae44819bf34a36592ed6b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623629"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>Метод ISymUnmanagedMethod::GetSequencePoints
Возвращает все точки следования в методе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cPoints`  
 [in] Объект `ULONG32` , получающий размер `offsets`, `documents`, `lines`, `columns`, `endLines`, и `endColumns` массивов.  
  
 `pcPoints`  
 [out] Указатель на `ULONG32` , получающий длину буфера, необходимый для точек следования.  
  
 `offsets`  
 [in] Массив, в которой будут храниться промежуточные Microsoft языка MSIL смещений от начала метода для точек следования.  
  
 `documents`  
 [in] Массив, в котором для хранения документов, в которых находятся точки следования.  
  
 `lines`  
 [in] Массив для хранения строк в документах, в которых находятся точки следования.  
  
 `columns`  
 [in] Массив, в котором для хранения этих столбцов в документах, в которых находятся точки следования.  
  
 `endLines`  
 [in] Массив строк в документах, в которых заканчиваются точки следования.  
  
 `endColumns`  
 [in] Массив столбцов в документах, в которых заканчиваются точки следования.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
