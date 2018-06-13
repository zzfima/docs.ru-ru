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
ms.openlocfilehash: ce9ce768e32434e0a1acd2fad67a0cdc99f49e18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430150"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="17bec-102">Метод ISymUnmanagedConstant::GetSignature</span><span class="sxs-lookup"><span data-stu-id="17bec-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="17bec-103">Возвращает подпись константы.</span><span class="sxs-lookup"><span data-stu-id="17bec-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17bec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17bec-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17bec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="17bec-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="17bec-106">[in] Длина буфера, `pcSig` указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="17bec-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="17bec-107">[out] Указатель на `ULONG32` , получающий размер в символах, буфера, необходимый для подписи.</span><span class="sxs-lookup"><span data-stu-id="17bec-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="17bec-108">[out] Буфер, содержит подписи.</span><span class="sxs-lookup"><span data-stu-id="17bec-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17bec-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="17bec-109">Return Value</span></span>  
 <span data-ttu-id="17bec-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="17bec-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17bec-111">Требования</span><span class="sxs-lookup"><span data-stu-id="17bec-111">Requirements</span></span>  
 <span data-ttu-id="17bec-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="17bec-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17bec-113">См. также</span><span class="sxs-lookup"><span data-stu-id="17bec-113">See Also</span></span>  
 [<span data-ttu-id="17bec-114">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="17bec-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="17bec-115">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="17bec-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="17bec-116">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="17bec-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
