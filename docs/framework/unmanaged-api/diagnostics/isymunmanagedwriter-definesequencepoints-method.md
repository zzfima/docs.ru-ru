---
title: Метод ISymUnmanagedWriter::DefineSequencePoints
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
ms.openlocfilehash: 63ba108bc234e566450bb019afc63acb4e75ad1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427981"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a>Метод ISymUnmanagedWriter::DefineSequencePoints
Определяет группу точек следования в текущем методе. Каждая начальная строка и начальный столбец определяют начало инструкции в методе. Каждая конечная строка и конечный столбец определяют конец оператора в методе. Массивы должны быть отсортированы в порядке возрастания смещений. Смещение всегда измеряется от начала метода в байтах.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `document`  
 окне Объект документа, для которого определяются точки следования.  
  
 `spCount`  
 окне `ULONG32`, указывающий размер каждого из буферов `offsets`, `lines`, `columns`, `endLines`и `endColumns`.  
  
 `offsets`  
 окне Смещение точек последовательности, измеряемое от начала метода.  
  
 `lines`  
 окне Начальные номера строк точек следования.  
  
 `columns`  
 окне Начальные номера столбцов точек следования.  
  
 `endLines`  
 окне Номера конечных строк точек следования. Этот параметр является необязательным.  
  
 `endColumns`  
 окне Конечные номера столбцов точек следования. Этот параметр является необязательным.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
