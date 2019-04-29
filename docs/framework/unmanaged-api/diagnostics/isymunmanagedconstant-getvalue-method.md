---
title: Метод ISymUnmanagedConstant::GetValue
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 75cc16f44ddf29b161c758718b697cc2aaba8e08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940027"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="36867-102">Метод ISymUnmanagedConstant::GetValue</span><span class="sxs-lookup"><span data-stu-id="36867-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="36867-103">Возвращает значение константы.</span><span class="sxs-lookup"><span data-stu-id="36867-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36867-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36867-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36867-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="36867-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="36867-106">[out] Указатель на переменную, получающую значение.</span><span class="sxs-lookup"><span data-stu-id="36867-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36867-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="36867-107">Return Value</span></span>  
 <span data-ttu-id="36867-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="36867-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36867-109">Требования</span><span class="sxs-lookup"><span data-stu-id="36867-109">Requirements</span></span>  
 <span data-ttu-id="36867-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="36867-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36867-111">См. также</span><span class="sxs-lookup"><span data-stu-id="36867-111">See also</span></span>

- [<span data-ttu-id="36867-112">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="36867-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="36867-113">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="36867-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="36867-114">Метод GetSignature</span><span class="sxs-lookup"><span data-stu-id="36867-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
