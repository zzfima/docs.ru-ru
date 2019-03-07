---
title: Метод ISymUnmanagedDocument::FindClosestLine
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 760a6feb8400e60b7e14bf244d66c9026031e5dc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474241"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a>Метод ISymUnmanagedDocument::FindClosestLine
Возвращает ближайшую строку, являющуюся точкой следования, для заданной строки в этом документе, которые могут поддерживаться или не может являться точкой следования.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  
 `line`  
 [in] Строка в этом документе.  
  
 `pRetVal`  
 [out] Указатель на переменную, которая получает строки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — код ошибки.  
  
## <a name="see-also"></a>См. также
- [Интерфейс ISymUnmanagedDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
