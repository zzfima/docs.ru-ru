---
title: Интерфейс ISymUnmanagedScope2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a33d8b489551dc69542e1b12bcf83602ec5a2008
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427252"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="c2089-102">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="c2089-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="c2089-103">Представляет лексическую область видимости в пределах одного метода.</span><span class="sxs-lookup"><span data-stu-id="c2089-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="c2089-104">Этот интерфейс расширяет интерфейс [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) интерфейс с методами, которые получают сведения о константы, определенные в области.</span><span class="sxs-lookup"><span data-stu-id="c2089-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2089-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c2089-105">Methods</span></span>  
  
|<span data-ttu-id="c2089-106">Метод</span><span class="sxs-lookup"><span data-stu-id="c2089-106">Method</span></span>|<span data-ttu-id="c2089-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c2089-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2089-108">Метод GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="c2089-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="c2089-109">Возвращает количество констант, определенных в данной области.</span><span class="sxs-lookup"><span data-stu-id="c2089-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="c2089-110">Метод GetConstants</span><span class="sxs-lookup"><span data-stu-id="c2089-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="c2089-111">Получает локальные константы, определенные в этой области.</span><span class="sxs-lookup"><span data-stu-id="c2089-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2089-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c2089-112">Requirements</span></span>  
 <span data-ttu-id="c2089-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c2089-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2089-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c2089-114">See Also</span></span>  
 [<span data-ttu-id="c2089-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="c2089-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="c2089-116">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="c2089-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
