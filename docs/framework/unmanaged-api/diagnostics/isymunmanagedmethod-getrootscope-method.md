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
ms.openlocfilehash: 7c77be0dde950693d3943e41c392dcdcd9bc995e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096079"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="acf19-102">Метод ISymUnmanagedMethod::GetRootScope</span><span class="sxs-lookup"><span data-stu-id="acf19-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="acf19-103">Возвращает корневую лексическую область, в этом методе.</span><span class="sxs-lookup"><span data-stu-id="acf19-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="acf19-104">Эта область включает весь метод.</span><span class="sxs-lookup"><span data-stu-id="acf19-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acf19-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="acf19-105">Syntax</span></span>  
  
```  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acf19-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="acf19-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="acf19-107">[out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="acf19-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acf19-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="acf19-108">Return Value</span></span>  
 <span data-ttu-id="acf19-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="acf19-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acf19-110">Требования</span><span class="sxs-lookup"><span data-stu-id="acf19-110">Requirements</span></span>  
 <span data-ttu-id="acf19-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="acf19-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf19-112">См. также</span><span class="sxs-lookup"><span data-stu-id="acf19-112">See also</span></span>

- [<span data-ttu-id="acf19-113">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="acf19-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
