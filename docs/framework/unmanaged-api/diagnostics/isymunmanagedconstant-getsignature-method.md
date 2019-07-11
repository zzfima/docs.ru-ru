---
title: Метод ISymUnmanagedConstant::GetSignature
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5d479e9f55cf7d7a13fef99f302bfd8d9d89d47f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776956"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="abbeb-102">Метод ISymUnmanagedConstant::GetSignature</span><span class="sxs-lookup"><span data-stu-id="abbeb-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="abbeb-103">Получает сигнатуру константы.</span><span class="sxs-lookup"><span data-stu-id="abbeb-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abbeb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abbeb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abbeb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="abbeb-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="abbeb-106">[in] Длина буфера, `pcSig` указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="abbeb-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="abbeb-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, необходимый для подписи.</span><span class="sxs-lookup"><span data-stu-id="abbeb-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="abbeb-108">[out] Буфер, который содержит подписи.</span><span class="sxs-lookup"><span data-stu-id="abbeb-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abbeb-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="abbeb-109">Return Value</span></span>  
 <span data-ttu-id="abbeb-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="abbeb-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abbeb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="abbeb-111">Requirements</span></span>  
 <span data-ttu-id="abbeb-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="abbeb-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abbeb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="abbeb-113">See also</span></span>

- [<span data-ttu-id="abbeb-114">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="abbeb-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="abbeb-115">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="abbeb-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="abbeb-116">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="abbeb-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
