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
ms.openlocfilehash: 96ad0e34bf638c378f37e317f790696c2ac7cb25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519701"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="2ab2a-102">Метод ISymUnmanagedDocument::FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="2ab2a-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="2ab2a-103">Возвращает ближайшую строку, являющуюся точкой следования, для заданной строки в этом документе, которые могут поддерживаться или не может являться точкой следования.</span><span class="sxs-lookup"><span data-stu-id="2ab2a-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ab2a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ab2a-104">Syntax</span></span>  
  
```  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ab2a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ab2a-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="2ab2a-106">[in] Строка в этом документе.</span><span class="sxs-lookup"><span data-stu-id="2ab2a-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="2ab2a-107">[out] Указатель на переменную, которая получает строки.</span><span class="sxs-lookup"><span data-stu-id="2ab2a-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ab2a-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2ab2a-108">Return Value</span></span>  
 <span data-ttu-id="2ab2a-109">Значение S_OK, если метод выполнен успешно; в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="2ab2a-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab2a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2ab2a-110">See also</span></span>
- [<span data-ttu-id="2ab2a-111">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="2ab2a-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
