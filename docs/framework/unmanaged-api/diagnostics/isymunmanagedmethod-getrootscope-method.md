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
ms.openlocfilehash: 8956d72d25f240eff653d3eefb92b68431f4e2ae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771783"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="47434-102">Метод ISymUnmanagedMethod::GetRootScope</span><span class="sxs-lookup"><span data-stu-id="47434-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="47434-103">Возвращает корневую лексическую область, в этом методе.</span><span class="sxs-lookup"><span data-stu-id="47434-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="47434-104">Эта область включает весь метод.</span><span class="sxs-lookup"><span data-stu-id="47434-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47434-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47434-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47434-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="47434-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="47434-107">[out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="47434-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47434-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="47434-108">Return Value</span></span>  
 <span data-ttu-id="47434-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="47434-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47434-110">Требования</span><span class="sxs-lookup"><span data-stu-id="47434-110">Requirements</span></span>  
 <span data-ttu-id="47434-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="47434-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47434-112">См. также</span><span class="sxs-lookup"><span data-stu-id="47434-112">See also</span></span>

- [<span data-ttu-id="47434-113">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="47434-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
