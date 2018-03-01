---
title: "Метод ISymUnmanagedDispose::Destroy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8d418bbb476fea306bf9ad92ce2b30d558627009
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="c85e4-102">Метод ISymUnmanagedDispose::Destroy</span><span class="sxs-lookup"><span data-stu-id="c85e4-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="c85e4-103">Вызывает базовый объект освободить все внутренние ссылки и возврата сбоя на каждом последующем вызове метода.</span><span class="sxs-lookup"><span data-stu-id="c85e4-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c85e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c85e4-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c85e4-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c85e4-105">Return Value</span></span>  
 <span data-ttu-id="c85e4-106">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="c85e4-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c85e4-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c85e4-107">Requirements</span></span>  
 <span data-ttu-id="c85e4-108">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c85e4-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c85e4-109">См. также</span><span class="sxs-lookup"><span data-stu-id="c85e4-109">See Also</span></span>  
 [<span data-ttu-id="c85e4-110">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="c85e4-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
