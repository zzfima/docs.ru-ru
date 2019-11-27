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
ms.openlocfilehash: 75d477af7395a9b7d3328b2a5787f810733f3749
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448874"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>Метод ISymUnmanagedMethod::GetSequencePoints
Возвращает все точки следования в этом методе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="parameters"></a>Параметры  
 `cPoints`  
 окне `ULONG32`, получающий размер массивов `offsets`, `documents`, `lines`, `columns`, `endLines`и `endColumns`.  
  
 `pcPoints`  
 заполняет Указатель на `ULONG32`, который получает длину буфера, необходимую для хранения точек следования.  
  
 `offsets`  
 окне Массив, в котором хранятся смещения MSIL от начала метода для точек следования.  
  
 `documents`  
 окне Массив, в котором хранятся документы, в которых находятся точки следования.  
  
 `lines`  
 окне Массив, в котором хранятся строки в документах, где находятся точки следования.  
  
 `columns`  
 окне Массив, в котором хранятся столбцы в документах, где находятся точки следования.  
  
 `endLines`  
 окне Массив строк в документах, в которых заканчивается точка следования.  
  
 `endColumns`  
 окне Массив столбцов в документах, в которых находятся конечные точки последовательности.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
