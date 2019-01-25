---
title: Метод ISymUnmanagedWriter2::DefineConstant2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e843acc82d52e2c7a772f4799e7bb0af8ecff10d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545729"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="387bc-102">Метод ISymUnmanagedWriter2::DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="387bc-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="387bc-103">Определяет имя для значения константы.</span><span class="sxs-lookup"><span data-stu-id="387bc-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="387bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="387bc-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="387bc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="387bc-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="387bc-106">[in] Постоянное имя.</span><span class="sxs-lookup"><span data-stu-id="387bc-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="387bc-107">[in] Значение константы.</span><span class="sxs-lookup"><span data-stu-id="387bc-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="387bc-108">[in] Токен метаданных константы.</span><span class="sxs-lookup"><span data-stu-id="387bc-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="387bc-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="387bc-109">Return Value</span></span>  
 <span data-ttu-id="387bc-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="387bc-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="387bc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="387bc-111">Requirements</span></span>  
 <span data-ttu-id="387bc-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="387bc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="387bc-113">См. также</span><span class="sxs-lookup"><span data-stu-id="387bc-113">See also</span></span>
- [<span data-ttu-id="387bc-114">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="387bc-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="387bc-115">Метод DefineConstant</span><span class="sxs-lookup"><span data-stu-id="387bc-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
