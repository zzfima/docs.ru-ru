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
ms.openlocfilehash: 6d4b5f94bdbb7319cef14c8b86f8ea995df7ff21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424486"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="b54aa-102">Метод ISymUnmanagedDispose::Destroy</span><span class="sxs-lookup"><span data-stu-id="b54aa-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="b54aa-103">Вызывает базовый объект освободить все внутренние ссылки и возврата сбоя на каждом последующем вызове метода.</span><span class="sxs-lookup"><span data-stu-id="b54aa-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b54aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b54aa-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b54aa-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b54aa-105">Return Value</span></span>  
 <span data-ttu-id="b54aa-106">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b54aa-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b54aa-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b54aa-107">Requirements</span></span>  
 <span data-ttu-id="b54aa-108">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b54aa-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b54aa-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b54aa-109">See Also</span></span>  
 [<span data-ttu-id="b54aa-110">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="b54aa-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
