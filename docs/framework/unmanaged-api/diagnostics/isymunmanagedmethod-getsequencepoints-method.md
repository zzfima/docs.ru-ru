---
title: "Метод ISymUnmanagedMethod::GetSequencePoints"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetSequencePoints
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 071cbb6c33b56cb4fb409ab634a89f589db5bab8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
 [out] Указатель на `ULONG32` , который получает длину буфера, требуемое для размещения точек следования.  
  
 `offsets`  
 [in] Массив, в котором для хранения промежуточных Microsoft (MSIL) смещений на языке от начала метода для точек следования.  
  
 `documents`  
 [in] Массив для хранения документов, в которых находятся точки следования.  
  
 `lines`  
 [in] Массив для сохранения строк в документах, в которых находятся точки следования.  
  
 `columns`  
 [in] Массив для хранения этих столбцов в документах, в которых находятся точки следования.  
  
 `endLines`  
 [in] Массив строк в документах, в которых заканчиваются точки следования.  
  
 `endColumns`  
 [in] Массив столбцов в документах, в которых заканчиваются точки следования.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
