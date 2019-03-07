---
title: Метод ISymUnmanagedScope::GetMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a18689563cb3d5fb8460893f9a429507cf93b8f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486970"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="9d221-102">Метод ISymUnmanagedScope::GetMethod</span><span class="sxs-lookup"><span data-stu-id="9d221-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="9d221-103">Возвращает метод, который содержит эту область.</span><span class="sxs-lookup"><span data-stu-id="9d221-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d221-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d221-104">Syntax</span></span>  
  
```  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d221-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d221-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="9d221-106">[out] Указатель на возвращенный [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9d221-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d221-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9d221-107">Return Value</span></span>  
 <span data-ttu-id="9d221-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="9d221-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d221-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9d221-109">Requirements</span></span>  
 <span data-ttu-id="9d221-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9d221-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d221-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9d221-111">See also</span></span>
- [<span data-ttu-id="9d221-112">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="9d221-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
