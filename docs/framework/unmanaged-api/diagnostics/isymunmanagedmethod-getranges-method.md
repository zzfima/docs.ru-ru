---
title: "Метод ISymUnmanagedMethod::GetRanges"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetRanges
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 71d24bc83d6a26c800d0d97e885b322cc2b4ccbd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetranges-method"></a>Метод ISymUnmanagedMethod::GetRanges
Заданной позиции в документе возвращает массив пар начального и конечного смещения, соответствующих диапазонам на языке MSIL занимаемым данной позицией в этом методе. Массив является массивом целых чисел и имеет формат [начала, окончания, начало, завершение]. Число пар диапазона является длина массива, деленному на 2.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `document`  
 [in] Документ, для которого запрашивается смещение.  
  
 `line`  
 [in] Строка документа, соответствующая этим диапазонам.  
  
 `column`  
 [in] Столбец документа, соответствующий этим диапазонам.  
  
 `cRanges`  
 [in] Размер массива `ranges`.  
  
 `pcRanges`  
 [out] Указатель на `ULONG32` , получающий размер буфера, должны содержать диапазоны.  
  
 `ranges`  
 [out] Указатель на буфер, получающий диапазоны.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [ISymUnmanagedMethod-интерфейс](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
