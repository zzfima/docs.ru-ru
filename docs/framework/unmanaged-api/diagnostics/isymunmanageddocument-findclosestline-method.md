---
title: "Метод ISymUnmanagedDocument::FindClosestLine"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.FindClosestLine
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8a4fff5ce5cdcde35c8483136cf4c3cd75854f6c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="48d39-102">Метод ISymUnmanagedDocument::FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="48d39-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="48d39-103">Возвращает ближайшую строку, являющуюся точкой следования, для заданной строки в этом документе, которые могут поддерживаться или не может являться точкой следования.</span><span class="sxs-lookup"><span data-stu-id="48d39-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48d39-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48d39-104">Syntax</span></span>  
  
```  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48d39-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="48d39-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="48d39-106">[in] Строка в этом документе.</span><span class="sxs-lookup"><span data-stu-id="48d39-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="48d39-107">[out] Указатель на переменную, которая получает строки.</span><span class="sxs-lookup"><span data-stu-id="48d39-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48d39-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="48d39-108">Return Value</span></span>  
 <span data-ttu-id="48d39-109">Значение S_OK, если метод выполнен успешно; в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="48d39-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d39-110">См. также</span><span class="sxs-lookup"><span data-stu-id="48d39-110">See Also</span></span>  
 [<span data-ttu-id="48d39-111">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="48d39-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
