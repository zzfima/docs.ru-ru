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
ms.openlocfilehash: 2939d9cf3991a9e0b8f93bb301925b1092eca50e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446048"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="f7c27-102">Метод ISymUnmanagedVariable::GetSignature</span><span class="sxs-lookup"><span data-stu-id="f7c27-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="f7c27-103">Возвращает сигнатуру этой переменной.</span><span class="sxs-lookup"><span data-stu-id="f7c27-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7c27-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7c27-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7c27-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7c27-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="f7c27-106">окне Длина буфера, на который указывает параметр `sig`.</span><span class="sxs-lookup"><span data-stu-id="f7c27-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="f7c27-107">заполняет Указатель на `ULONG32`, который получает размер (в символах) буфера, необходимого для хранения подписи.</span><span class="sxs-lookup"><span data-stu-id="f7c27-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="f7c27-108">заполняет Буфер, в котором хранится подпись.</span><span class="sxs-lookup"><span data-stu-id="f7c27-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7c27-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f7c27-109">Return Value</span></span>  
 <span data-ttu-id="f7c27-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f7c27-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7c27-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f7c27-111">Requirements</span></span>  
 <span data-ttu-id="f7c27-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="f7c27-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c27-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="f7c27-113">See also</span></span>

- [<span data-ttu-id="f7c27-114">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="f7c27-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
