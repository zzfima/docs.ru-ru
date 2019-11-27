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
ms.openlocfilehash: e930a9a3753ccf2b8aff798916c876fbedad4df4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430705"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="3fce9-102">Метод ISymUnmanagedDispose::Destroy</span><span class="sxs-lookup"><span data-stu-id="3fce9-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="3fce9-103">Заставляет базовый объект освобождать все внутренние ссылки и возвращать ошибку при любом последующем вызове метода.</span><span class="sxs-lookup"><span data-stu-id="3fce9-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fce9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3fce9-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3fce9-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3fce9-105">Return Value</span></span>  
 <span data-ttu-id="3fce9-106">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="3fce9-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fce9-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3fce9-107">Requirements</span></span>  
 <span data-ttu-id="3fce9-108">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="3fce9-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fce9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="3fce9-109">See also</span></span>

- [<span data-ttu-id="3fce9-110">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="3fce9-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
