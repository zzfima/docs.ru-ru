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
ms.openlocfilehash: adad8854052d76476076e5e1357f6d3e2dec1052
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629479"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="f6ff8-102">Метод ISymUnmanagedDocument::GetDocumentType</span><span class="sxs-lookup"><span data-stu-id="f6ff8-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>
<span data-ttu-id="f6ff8-103">Получает тип документа в этом документе.</span><span class="sxs-lookup"><span data-stu-id="f6ff8-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6ff8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6ff8-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6ff8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6ff8-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f6ff8-106">[out] Указатель на переменную, которая получает тип документа.</span><span class="sxs-lookup"><span data-stu-id="f6ff8-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6ff8-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f6ff8-107">Return Value</span></span>  
 <span data-ttu-id="f6ff8-108">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="f6ff8-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ff8-109">См. также</span><span class="sxs-lookup"><span data-stu-id="f6ff8-109">See also</span></span>
- [<span data-ttu-id="f6ff8-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="f6ff8-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
