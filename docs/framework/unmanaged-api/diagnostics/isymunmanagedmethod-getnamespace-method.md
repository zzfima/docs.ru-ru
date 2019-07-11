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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 676c968bb48e493f9a4514235fbc3246cf395228
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774645"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="bafc3-102">Метод ISymUnmanagedMethod::GetNamespace</span><span class="sxs-lookup"><span data-stu-id="bafc3-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="bafc3-103">Получает пространство имен, в котором определен этот метод.</span><span class="sxs-lookup"><span data-stu-id="bafc3-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bafc3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bafc3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bafc3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bafc3-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="bafc3-106">[out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="bafc3-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bafc3-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bafc3-107">Return Value</span></span>  
 <span data-ttu-id="bafc3-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="bafc3-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bafc3-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bafc3-109">Requirements</span></span>  
 <span data-ttu-id="bafc3-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bafc3-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bafc3-111">См. также</span><span class="sxs-lookup"><span data-stu-id="bafc3-111">See also</span></span>

- [<span data-ttu-id="bafc3-112">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="bafc3-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
