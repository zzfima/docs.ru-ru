---
title: "Метод ISymUnmanagedReader::GetDocuments"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetDocuments
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 423267f30459c409cc1bba6e0dee53b31a2783cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="01b0b-102">Метод ISymUnmanagedReader::GetDocuments</span><span class="sxs-lookup"><span data-stu-id="01b0b-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="01b0b-103">Возвращает массив всех документов, определенных в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="01b0b-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01b0b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01b0b-104">Syntax</span></span>  
  
```  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01b0b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="01b0b-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="01b0b-106">[in] Размер массива `pDocs`.</span><span class="sxs-lookup"><span data-stu-id="01b0b-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="01b0b-107">[out] Указатель на переменную, которая получает длину массива.</span><span class="sxs-lookup"><span data-stu-id="01b0b-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="01b0b-108">[out] Указатель на переменную, которая получает массив документа.</span><span class="sxs-lookup"><span data-stu-id="01b0b-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01b0b-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="01b0b-109">Return Value</span></span>  
 <span data-ttu-id="01b0b-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="01b0b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01b0b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="01b0b-111">Requirements</span></span>  
 <span data-ttu-id="01b0b-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="01b0b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01b0b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="01b0b-113">See Also</span></span>  
 [<span data-ttu-id="01b0b-114">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="01b0b-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
