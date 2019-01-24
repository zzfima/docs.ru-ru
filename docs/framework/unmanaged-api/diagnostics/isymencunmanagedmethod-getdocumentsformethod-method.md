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
ms.openlocfilehash: cd294037774721839b0c4f1f09bdc2a6e3b87841
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562678"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="4de53-102">Метод ISymENCUnmanagedMethod::GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="4de53-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="4de53-103">Возвращает документы, которые этот метод имеет строки.</span><span class="sxs-lookup"><span data-stu-id="4de53-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4de53-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4de53-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,   
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4de53-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4de53-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="4de53-106">[in] Размер буфера, на который указывает `pcDocs`.</span><span class="sxs-lookup"><span data-stu-id="4de53-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="4de53-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения документов.</span><span class="sxs-lookup"><span data-stu-id="4de53-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="4de53-108">[in] Буфер, содержащий документы.</span><span class="sxs-lookup"><span data-stu-id="4de53-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4de53-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4de53-109">Return Value</span></span>  
 <span data-ttu-id="4de53-110">Значение S_OK, если метод выполнен успешно; в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="4de53-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4de53-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4de53-111">Requirements</span></span>  
 <span data-ttu-id="4de53-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4de53-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de53-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4de53-113">See also</span></span>
- [<span data-ttu-id="4de53-114">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="4de53-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
