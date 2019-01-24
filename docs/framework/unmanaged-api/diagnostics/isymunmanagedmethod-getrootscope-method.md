---
title: Метод ISymUnmanagedMethod::GetRootScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 458f6ab4a6848ce6921542ca62fe6d5c7cf4719f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704645"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="066c7-102">Метод ISymUnmanagedMethod::GetRootScope</span><span class="sxs-lookup"><span data-stu-id="066c7-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="066c7-103">Возвращает корневую лексическую область, в этом методе.</span><span class="sxs-lookup"><span data-stu-id="066c7-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="066c7-104">Эта область включает весь метод.</span><span class="sxs-lookup"><span data-stu-id="066c7-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="066c7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="066c7-105">Syntax</span></span>  
  
```  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="066c7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="066c7-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="066c7-107">[out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="066c7-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="066c7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="066c7-108">Return Value</span></span>  
 <span data-ttu-id="066c7-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="066c7-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="066c7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="066c7-110">Requirements</span></span>  
 <span data-ttu-id="066c7-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="066c7-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="066c7-112">См. также</span><span class="sxs-lookup"><span data-stu-id="066c7-112">See also</span></span>
- [<span data-ttu-id="066c7-113">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="066c7-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
