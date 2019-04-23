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
ms.openlocfilehash: cfd466f48a55f8b8905f6c76cf876fb8a32d4a8f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151402"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="4d0ab-102">Метод ISymUnmanagedMethod::GetNamespace</span><span class="sxs-lookup"><span data-stu-id="4d0ab-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="4d0ab-103">Получает пространство имен, в котором определен этот метод.</span><span class="sxs-lookup"><span data-stu-id="4d0ab-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d0ab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d0ab-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d0ab-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d0ab-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4d0ab-106">[out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4d0ab-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d0ab-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4d0ab-107">Return Value</span></span>  
 <span data-ttu-id="4d0ab-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="4d0ab-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d0ab-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4d0ab-109">Requirements</span></span>  
 <span data-ttu-id="4d0ab-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4d0ab-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d0ab-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4d0ab-111">See also</span></span>

- [<span data-ttu-id="4d0ab-112">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="4d0ab-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
