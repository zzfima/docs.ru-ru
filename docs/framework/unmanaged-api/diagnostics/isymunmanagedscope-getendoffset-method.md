---
title: Метод ISymUnmanagedScope::GetEndOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
ms.openlocfilehash: 25a8188e3ab62c095355b72b3e63e767a6768114
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446353"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="92ba1-102">Метод ISymUnmanagedScope::GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="92ba1-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="92ba1-103">Gets the end offset for this scope.</span><span class="sxs-lookup"><span data-stu-id="92ba1-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ba1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92ba1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92ba1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="92ba1-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="92ba1-106">[out] A pointer to a `ULONG32` that receives the end offset.</span><span class="sxs-lookup"><span data-stu-id="92ba1-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92ba1-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="92ba1-107">Return Value</span></span>  
 <span data-ttu-id="92ba1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="92ba1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92ba1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="92ba1-109">Requirements</span></span>  
 <span data-ttu-id="92ba1-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="92ba1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ba1-111">См. также</span><span class="sxs-lookup"><span data-stu-id="92ba1-111">See also</span></span>

- [<span data-ttu-id="92ba1-112">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="92ba1-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="92ba1-113">Метод GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="92ba1-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
