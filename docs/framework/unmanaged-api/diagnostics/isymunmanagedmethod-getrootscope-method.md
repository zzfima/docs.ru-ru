---
title: "Метод ISymUnmanagedMethod::GetRootScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetRootScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 82b03e6db75d69d1d36f0137922448bad165e6ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="4723b-102">Метод ISymUnmanagedMethod::GetRootScope</span><span class="sxs-lookup"><span data-stu-id="4723b-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="4723b-103">Возвращает корневую лексическую область в этом методе.</span><span class="sxs-lookup"><span data-stu-id="4723b-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="4723b-104">Эта область включает весь метод.</span><span class="sxs-lookup"><span data-stu-id="4723b-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4723b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4723b-105">Syntax</span></span>  
  
```  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4723b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4723b-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4723b-107">[out] Указатель, который задается в возвращаемую [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4723b-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4723b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4723b-108">Return Value</span></span>  
 <span data-ttu-id="4723b-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="4723b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4723b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4723b-110">Requirements</span></span>  
 <span data-ttu-id="4723b-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4723b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4723b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4723b-112">See Also</span></span>  
 [<span data-ttu-id="4723b-113">ISymUnmanagedMethod-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4723b-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
