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
ms.openlocfilehash: 90f5924bc03a9896442fd61a4c618d18ed999faf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638877"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="bdefc-102">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="bdefc-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="bdefc-103">Освобождает неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="bdefc-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bdefc-104">Методы</span><span class="sxs-lookup"><span data-stu-id="bdefc-104">Methods</span></span>  
  
|<span data-ttu-id="bdefc-105">Метод</span><span class="sxs-lookup"><span data-stu-id="bdefc-105">Method</span></span>|<span data-ttu-id="bdefc-106">Описание</span><span class="sxs-lookup"><span data-stu-id="bdefc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bdefc-107">Метод Destroy</span><span class="sxs-lookup"><span data-stu-id="bdefc-107">Destroy Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-destroy-method.md)|<span data-ttu-id="bdefc-108">Заставляет объект освободить все внутренние ссылки и сбой запроса на каждом последующем вызове метода.</span><span class="sxs-lookup"><span data-stu-id="bdefc-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bdefc-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bdefc-109">Requirements</span></span>  
 <span data-ttu-id="bdefc-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bdefc-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdefc-111">См. также</span><span class="sxs-lookup"><span data-stu-id="bdefc-111">See also</span></span>
- [<span data-ttu-id="bdefc-112">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="bdefc-112">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
