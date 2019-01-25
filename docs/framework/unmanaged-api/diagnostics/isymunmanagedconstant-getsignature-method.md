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
ms.openlocfilehash: 86c64f7c56555619ead495e1e935e7bea86ac6ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495452"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="d642e-102">Метод ISymUnmanagedConstant::GetSignature</span><span class="sxs-lookup"><span data-stu-id="d642e-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="d642e-103">Получает сигнатуру константы.</span><span class="sxs-lookup"><span data-stu-id="d642e-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d642e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d642e-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d642e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d642e-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="d642e-106">[in] Длина буфера, `pcSig` указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="d642e-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="d642e-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, необходимый для подписи.</span><span class="sxs-lookup"><span data-stu-id="d642e-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="d642e-108">[out] Буфер, который содержит подписи.</span><span class="sxs-lookup"><span data-stu-id="d642e-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d642e-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d642e-109">Return Value</span></span>  
 <span data-ttu-id="d642e-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="d642e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d642e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d642e-111">Requirements</span></span>  
 <span data-ttu-id="d642e-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d642e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d642e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d642e-113">See also</span></span>
- [<span data-ttu-id="d642e-114">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="d642e-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="d642e-115">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="d642e-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="d642e-116">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="d642e-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
