---
title: Метод ISymUnmanagedDocument::GetDocumentType
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetDocumentType
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0460086874af38cad348c965237f8c423f18e868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436004"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="58794-102">Метод ISymUnmanagedDocument::GetDocumentType</span><span class="sxs-lookup"><span data-stu-id="58794-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>
<span data-ttu-id="58794-103">Возвращает тип этого документа.</span><span class="sxs-lookup"><span data-stu-id="58794-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58794-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58794-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58794-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="58794-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="58794-106">[out] Указатель на переменную, которая получает тип документа.</span><span class="sxs-lookup"><span data-stu-id="58794-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58794-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="58794-107">Return Value</span></span>  
 <span data-ttu-id="58794-108">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="58794-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58794-109">См. также</span><span class="sxs-lookup"><span data-stu-id="58794-109">See Also</span></span>  
 [<span data-ttu-id="58794-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="58794-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
