---
title: Метод ISymUnmanagedMethod::GetNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
ms.openlocfilehash: b8bbedb4c60a2df6070373f2b6a104fff094869a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448965"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="e54ca-102">Метод ISymUnmanagedMethod::GetNamespace</span><span class="sxs-lookup"><span data-stu-id="e54ca-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="e54ca-103">Возвращает пространство имен, в котором определен этот метод.</span><span class="sxs-lookup"><span data-stu-id="e54ca-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e54ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e54ca-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e54ca-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e54ca-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e54ca-106">заполняет Указатель, которому присваивается возвращаемый интерфейс [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e54ca-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e54ca-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e54ca-107">Return Value</span></span>  
 <span data-ttu-id="e54ca-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="e54ca-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e54ca-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e54ca-109">Requirements</span></span>  
 <span data-ttu-id="e54ca-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="e54ca-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e54ca-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="e54ca-111">See also</span></span>

- [<span data-ttu-id="e54ca-112">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="e54ca-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
