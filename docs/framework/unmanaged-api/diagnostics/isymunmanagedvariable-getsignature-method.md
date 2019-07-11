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
ms.openlocfilehash: abd4bb00f5c1e703740462f1709407616ac8a8e8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778237"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="63d44-102">Метод ISymUnmanagedVariable::GetSignature</span><span class="sxs-lookup"><span data-stu-id="63d44-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="63d44-103">Возвращает подпись переменной.</span><span class="sxs-lookup"><span data-stu-id="63d44-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63d44-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63d44-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="63d44-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="63d44-106">[in] Размер буфера, на который указывает `sig` параметра.</span><span class="sxs-lookup"><span data-stu-id="63d44-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="63d44-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, необходимый для подписи.</span><span class="sxs-lookup"><span data-stu-id="63d44-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="63d44-108">[out] Буфер, который содержит подписи.</span><span class="sxs-lookup"><span data-stu-id="63d44-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63d44-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="63d44-109">Return Value</span></span>  
 <span data-ttu-id="63d44-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="63d44-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d44-111">Требования</span><span class="sxs-lookup"><span data-stu-id="63d44-111">Requirements</span></span>  
 <span data-ttu-id="63d44-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="63d44-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d44-113">См. также</span><span class="sxs-lookup"><span data-stu-id="63d44-113">See also</span></span>

- [<span data-ttu-id="63d44-114">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="63d44-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
