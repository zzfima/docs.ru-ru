---
title: Метод ISymUnmanagedReader::GetDocuments
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0bcb0efab3b61f55bd5fdd3405799c7ac78ee521
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedreadergetdocuments-method"></a>Метод ISymUnmanagedReader::GetDocuments
Возвращает массив всех документов, определенных в хранилище символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cDocs`  
 [in] Размер массива `pDocs`.  
  
 `pcDocs`  
 [out] Указатель на переменную, которая получает длину массива.  
  
 `pDocs`  
 [out] Указатель на переменную, которая получает массив документа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
