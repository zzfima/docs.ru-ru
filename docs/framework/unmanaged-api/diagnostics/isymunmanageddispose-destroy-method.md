---
title: Метод ISymUnmanagedDispose::Destroy
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51d2f0aedffdd88974a8184954ecbb9a231b70c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213682"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="7b571-102">Метод ISymUnmanagedDispose::Destroy</span><span class="sxs-lookup"><span data-stu-id="7b571-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="7b571-103">Заставляет объект освободить все внутренние ссылки и сбой запроса на каждом последующем вызове метода.</span><span class="sxs-lookup"><span data-stu-id="7b571-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b571-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b571-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7b571-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7b571-105">Return Value</span></span>  
 <span data-ttu-id="7b571-106">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="7b571-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b571-107">Требования</span><span class="sxs-lookup"><span data-stu-id="7b571-107">Requirements</span></span>  
 <span data-ttu-id="7b571-108">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7b571-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b571-109">См. также</span><span class="sxs-lookup"><span data-stu-id="7b571-109">See also</span></span>

- [<span data-ttu-id="7b571-110">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="7b571-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
