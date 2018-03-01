---
title: "Метод ISymUnmanagedReader2::GetMethodsInDocument"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 175ab55c849a1457cafc46b29d67e5d22a42ee6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="8a84d-102">Метод ISymUnmanagedReader2::GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="8a84d-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="8a84d-103">Возвращает каждого метода, который содержит сведения о строке в указанный документ.</span><span class="sxs-lookup"><span data-stu-id="8a84d-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a84d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a84d-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a84d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a84d-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="8a84d-106">[in] Указатель на документ.</span><span class="sxs-lookup"><span data-stu-id="8a84d-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="8a84d-107">[in] Объект `ULONG32` указывает размер `pRetVal` массива.</span><span class="sxs-lookup"><span data-stu-id="8a84d-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="8a84d-108">[out] Указатель на `ULONG32` , получающий размер буфера, необходимый для методов.</span><span class="sxs-lookup"><span data-stu-id="8a84d-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="8a84d-109">[out] Указатель на буфер, получающий методы.</span><span class="sxs-lookup"><span data-stu-id="8a84d-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a84d-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8a84d-110">Return Value</span></span>  
 <span data-ttu-id="8a84d-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="8a84d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a84d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8a84d-112">Requirements</span></span>  
 <span data-ttu-id="8a84d-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8a84d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a84d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8a84d-114">See Also</span></span>  
 [<span data-ttu-id="8a84d-115">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="8a84d-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
