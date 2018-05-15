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
ms.openlocfilehash: 4b089540f23659d4f7811d921364adc73fd62803
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="d2e9f-102">Метод ISymUnmanagedVariable::GetSignature</span><span class="sxs-lookup"><span data-stu-id="d2e9f-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="d2e9f-103">Возвращает подпись переменной.</span><span class="sxs-lookup"><span data-stu-id="d2e9f-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2e9f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2e9f-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2e9f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d2e9f-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="d2e9f-106">[in] Размер буфера, на который указывает `sig` параметра.</span><span class="sxs-lookup"><span data-stu-id="d2e9f-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="d2e9f-107">[out] Указатель на `ULONG32` , получающий размер в символах, буфера, необходимый для подписи.</span><span class="sxs-lookup"><span data-stu-id="d2e9f-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="d2e9f-108">[out] Буфер, содержит подписи.</span><span class="sxs-lookup"><span data-stu-id="d2e9f-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2e9f-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d2e9f-109">Return Value</span></span>  
 <span data-ttu-id="d2e9f-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="d2e9f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2e9f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d2e9f-111">Requirements</span></span>  
 <span data-ttu-id="d2e9f-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d2e9f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2e9f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d2e9f-113">See Also</span></span>  
 [<span data-ttu-id="d2e9f-114">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="d2e9f-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
