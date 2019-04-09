---
title: Метод ISymUnmanagedReader2::GetMethodsInDocument
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28b240159c36b03b2c476f56f7e6ad7b33f20649
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142354"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="dccfb-102">Метод ISymUnmanagedReader2::GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="dccfb-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="dccfb-103">Возвращает каждый метод, который содержит сведения о строке в указанный документ.</span><span class="sxs-lookup"><span data-stu-id="dccfb-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dccfb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dccfb-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dccfb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dccfb-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="dccfb-106">[in] Указатель на документ.</span><span class="sxs-lookup"><span data-stu-id="dccfb-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="dccfb-107">[in] Объект `ULONG32` указывает размер `pRetVal` массива.</span><span class="sxs-lookup"><span data-stu-id="dccfb-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="dccfb-108">[out] Указатель на `ULONG32` , получающий размер буфера, необходимый для методов.</span><span class="sxs-lookup"><span data-stu-id="dccfb-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="dccfb-109">[out] Указатель на буфер, получающий методы.</span><span class="sxs-lookup"><span data-stu-id="dccfb-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dccfb-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dccfb-110">Return Value</span></span>  
 <span data-ttu-id="dccfb-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="dccfb-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dccfb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="dccfb-112">Requirements</span></span>  
 <span data-ttu-id="dccfb-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dccfb-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dccfb-114">См. также</span><span class="sxs-lookup"><span data-stu-id="dccfb-114">See also</span></span>

- [<span data-ttu-id="dccfb-115">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="dccfb-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
