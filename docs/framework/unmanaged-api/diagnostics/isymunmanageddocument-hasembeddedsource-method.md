---
title: Метод ISymUnmanagedDocument::HasEmbeddedSource
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d6c79be95ff80c8de9b07cb33be46a5f5db22b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094272"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="5d4c1-102">Метод ISymUnmanagedDocument::HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="5d4c1-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="5d4c1-103">Возвращает `true` , содержит ли документ источника, внедренный в символы отладки; в противном случае возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="5d4c1-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d4c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d4c1-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d4c1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d4c1-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="5d4c1-106">[out] Указатель на переменную, которая указывает, имеет ли документ источника, внедренный в символы отладки.</span><span class="sxs-lookup"><span data-stu-id="5d4c1-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d4c1-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5d4c1-107">Return Value</span></span>  
 <span data-ttu-id="5d4c1-108">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="5d4c1-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d4c1-109">См. также</span><span class="sxs-lookup"><span data-stu-id="5d4c1-109">See also</span></span>

- [<span data-ttu-id="5d4c1-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="5d4c1-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
