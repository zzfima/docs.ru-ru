---
title: Метод ISymUnmanagedMethod::GetSourceStartEnd
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1e15bab136540c73f8e1cff0e6bb52ec1d6c0063
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426228"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a>Метод ISymUnmanagedMethod::GetSourceStartEnd
Возвращает начальную и конечную позицию документа источника этого метода. Массив отсчитывается от начала, а вторая позиция массива написан.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
#### <a name="parameters"></a>Параметры  
 `docs`  
 [in] Начальный и конечный исходные документы.  
  
 `lines`  
 [in] Начальная и конечная строки соответствующих исходных документов.  
  
 `columns`  
 [in] Начальный и конечный столбцы соответствующих исходных документов.  
  
 `pRetVal`  
 [out] `true` если позиции определены; в противном случае — `false`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
