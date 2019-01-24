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
ms.openlocfilehash: beb48835039f142ea1d9e18871f77ada1b6f4f3e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706317"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="62049-102">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="62049-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="62049-103">Представляет лексическую область внутри метода.</span><span class="sxs-lookup"><span data-stu-id="62049-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="62049-104">Этот интерфейс расширяет [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) интерфейс с методами, которые получают сведения о константы, определенные в области действия.</span><span class="sxs-lookup"><span data-stu-id="62049-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62049-105">Методы</span><span class="sxs-lookup"><span data-stu-id="62049-105">Methods</span></span>  
  
|<span data-ttu-id="62049-106">Метод</span><span class="sxs-lookup"><span data-stu-id="62049-106">Method</span></span>|<span data-ttu-id="62049-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="62049-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62049-108">Метод GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="62049-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="62049-109">Получает число констант, определенных в этой области.</span><span class="sxs-lookup"><span data-stu-id="62049-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="62049-110">Метод GetConstants</span><span class="sxs-lookup"><span data-stu-id="62049-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="62049-111">Возвращает локальные константы, определенные в этой области.</span><span class="sxs-lookup"><span data-stu-id="62049-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="62049-112">Требования</span><span class="sxs-lookup"><span data-stu-id="62049-112">Requirements</span></span>  
 <span data-ttu-id="62049-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="62049-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62049-114">См. также</span><span class="sxs-lookup"><span data-stu-id="62049-114">See also</span></span>
- [<span data-ttu-id="62049-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="62049-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="62049-116">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="62049-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
