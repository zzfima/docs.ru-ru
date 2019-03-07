---
title: Метод ISymUnmanagedVariable::GetSignature
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f28d6ec882afb21c3c204e141b1b6d883793004
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499060"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="ff2ea-102">Метод ISymUnmanagedVariable::GetSignature</span><span class="sxs-lookup"><span data-stu-id="ff2ea-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="ff2ea-103">Возвращает подпись переменной.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff2ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff2ea-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff2ea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff2ea-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="ff2ea-106">[in] Размер буфера, на который указывает `sig` параметра.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="ff2ea-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, необходимый для подписи.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="ff2ea-108">[out] Буфер, который содержит подписи.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff2ea-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ff2ea-109">Return Value</span></span>  
 <span data-ttu-id="ff2ea-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff2ea-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ff2ea-111">Requirements</span></span>  
 <span data-ttu-id="ff2ea-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ff2ea-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff2ea-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ff2ea-113">See also</span></span>
- [<span data-ttu-id="ff2ea-114">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="ff2ea-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
