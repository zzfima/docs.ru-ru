---
title: "Метод ISymUnmanagedWriter::DefineDocument"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 638759cb52eb28cc79217da81a867f2593e1ae97
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterdefinedocument-method"></a>Метод ISymUnmanagedWriter::DefineDocument
Определяет исходный документ. Для известных языков, поставщиков и типов документов предоставляются идентификаторы GUID.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
#### <a name="parameters"></a>Параметры  
 `url`  
 [in] Указатель на `WCHAR` , определяющий унифицированный указатель ресурса (URL) для идентификации документа.  
  
 `language`  
 [in] Указатель на идентификатор GUID, который определяет язык документа.  
  
 `languageVendor`  
 [in] Указатель на идентификатор GUID, который определяет удостоверение поставщика языка документа.  
  
 `documentType`  
 [in] Указатель на идентификатор GUID, который определяет тип документа.  
  
 `pRetVal`  
 [out] Указатель на возвращаемый [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) интерфейса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [ISymUnmanagedWriter-интерфейс](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
