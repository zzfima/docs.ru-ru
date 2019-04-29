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
ms.openlocfilehash: 7694c9b736700466ac1299b9632440e133109288
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939897"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="47a28-102">Метод ISymUnmanagedDocument::GetDocumentType</span><span class="sxs-lookup"><span data-stu-id="47a28-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>
<span data-ttu-id="47a28-103">Получает тип документа в этом документе.</span><span class="sxs-lookup"><span data-stu-id="47a28-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47a28-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47a28-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47a28-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="47a28-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="47a28-106">[out] Указатель на переменную, которая получает тип документа.</span><span class="sxs-lookup"><span data-stu-id="47a28-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47a28-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="47a28-107">Return Value</span></span>  
 <span data-ttu-id="47a28-108">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="47a28-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a28-109">См. также</span><span class="sxs-lookup"><span data-stu-id="47a28-109">See also</span></span>

- [<span data-ttu-id="47a28-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="47a28-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
