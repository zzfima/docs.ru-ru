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
ms.openlocfilehash: 401dfbea0da309db24f3052f462daa66e8bbef4a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449271"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="5b3de-102">Метод ISymUnmanagedConstant::GetSignature</span><span class="sxs-lookup"><span data-stu-id="5b3de-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="5b3de-103">Возвращает сигнатуру константы.</span><span class="sxs-lookup"><span data-stu-id="5b3de-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b3de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b3de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b3de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b3de-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="5b3de-106">окне Длина буфера, на который указывает параметр `pcSig`.</span><span class="sxs-lookup"><span data-stu-id="5b3de-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="5b3de-107">заполняет Указатель на `ULONG32`, который получает размер (в символах) буфера, необходимого для хранения подписи.</span><span class="sxs-lookup"><span data-stu-id="5b3de-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="5b3de-108">заполняет Буфер, в котором хранится подпись.</span><span class="sxs-lookup"><span data-stu-id="5b3de-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b3de-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5b3de-109">Return Value</span></span>  
 <span data-ttu-id="5b3de-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="5b3de-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b3de-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5b3de-111">Requirements</span></span>  
 <span data-ttu-id="5b3de-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="5b3de-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b3de-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5b3de-113">See also</span></span>

- [<span data-ttu-id="5b3de-114">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="5b3de-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="5b3de-115">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="5b3de-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="5b3de-116">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="5b3de-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
