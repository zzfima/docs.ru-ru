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
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="baa4c-102">Метод ISymUnmanagedReader::GetDocuments</span><span class="sxs-lookup"><span data-stu-id="baa4c-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="baa4c-103">Возвращает массив всех документов, определенных в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="baa4c-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baa4c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="baa4c-104">Syntax</span></span>  
  
```  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="baa4c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="baa4c-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="baa4c-106">[in] Размер массива `pDocs`.</span><span class="sxs-lookup"><span data-stu-id="baa4c-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="baa4c-107">[out] Указатель на переменную, которая получает длину массива.</span><span class="sxs-lookup"><span data-stu-id="baa4c-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="baa4c-108">[out] Указатель на переменную, которая получает массив документа.</span><span class="sxs-lookup"><span data-stu-id="baa4c-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="baa4c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="baa4c-109">Return Value</span></span>  
 <span data-ttu-id="baa4c-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="baa4c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baa4c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="baa4c-111">Requirements</span></span>  
 <span data-ttu-id="baa4c-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="baa4c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa4c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="baa4c-113">See Also</span></span>  
 [<span data-ttu-id="baa4c-114">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="baa4c-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
