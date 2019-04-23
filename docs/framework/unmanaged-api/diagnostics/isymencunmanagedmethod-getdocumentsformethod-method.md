---
title: Метод ISymENCUnmanagedMethod::GetDocumentsForMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db119a94cb7df29697836ffda240c29a86922d60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214784"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="64e3a-102">Метод ISymENCUnmanagedMethod::GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="64e3a-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="64e3a-103">Возвращает документы, которые этот метод имеет строки.</span><span class="sxs-lookup"><span data-stu-id="64e3a-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64e3a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64e3a-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,   
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64e3a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="64e3a-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="64e3a-106">[in] Размер буфера, на который указывает `pcDocs`.</span><span class="sxs-lookup"><span data-stu-id="64e3a-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="64e3a-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения документов.</span><span class="sxs-lookup"><span data-stu-id="64e3a-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="64e3a-108">[in] Буфер, содержащий документы.</span><span class="sxs-lookup"><span data-stu-id="64e3a-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64e3a-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="64e3a-109">Return Value</span></span>  
 <span data-ttu-id="64e3a-110">Значение S_OK, если метод выполнен успешно; в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="64e3a-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64e3a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="64e3a-111">Requirements</span></span>  
 <span data-ttu-id="64e3a-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="64e3a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64e3a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="64e3a-113">See also</span></span>

- [<span data-ttu-id="64e3a-114">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="64e3a-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
