---
title: Интерфейс ISymUnmanagedDispose
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose
helpviewer_keywords:
- ISymUnmanagedDispose interface [.NET Framework debugging]
ms.assetid: b1d74e83-a200-4d00-8fbd-27918808616d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8e81cea13fb8d25701ccbe163f112904baf47a9f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143173"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="62647-102">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="62647-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="62647-103">Освобождает неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="62647-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62647-104">Методы</span><span class="sxs-lookup"><span data-stu-id="62647-104">Methods</span></span>  
  
|<span data-ttu-id="62647-105">Метод</span><span class="sxs-lookup"><span data-stu-id="62647-105">Method</span></span>|<span data-ttu-id="62647-106">Описание</span><span class="sxs-lookup"><span data-stu-id="62647-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62647-107">Метод Destroy</span><span class="sxs-lookup"><span data-stu-id="62647-107">Destroy Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-destroy-method.md)|<span data-ttu-id="62647-108">Заставляет объект освободить все внутренние ссылки и сбой запроса на каждом последующем вызове метода.</span><span class="sxs-lookup"><span data-stu-id="62647-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="62647-109">Требования</span><span class="sxs-lookup"><span data-stu-id="62647-109">Requirements</span></span>  
 <span data-ttu-id="62647-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="62647-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62647-111">См. также</span><span class="sxs-lookup"><span data-stu-id="62647-111">See also</span></span>

- [<span data-ttu-id="62647-112">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="62647-112">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
