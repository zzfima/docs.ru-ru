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
ms.openlocfilehash: 0109b25b1cdc42204fc4873577e495641c4ec4fd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131460"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="fa92d-102">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="fa92d-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="fa92d-103">Представляет лексическую область внутри метода.</span><span class="sxs-lookup"><span data-stu-id="fa92d-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="fa92d-104">Этот интерфейс расширяет [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) интерфейс с методами, которые получают сведения о константы, определенные в области действия.</span><span class="sxs-lookup"><span data-stu-id="fa92d-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa92d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="fa92d-105">Methods</span></span>  
  
|<span data-ttu-id="fa92d-106">Метод</span><span class="sxs-lookup"><span data-stu-id="fa92d-106">Method</span></span>|<span data-ttu-id="fa92d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fa92d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa92d-108">Метод GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="fa92d-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="fa92d-109">Получает число констант, определенных в этой области.</span><span class="sxs-lookup"><span data-stu-id="fa92d-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="fa92d-110">Метод GetConstants</span><span class="sxs-lookup"><span data-stu-id="fa92d-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="fa92d-111">Возвращает локальные константы, определенные в этой области.</span><span class="sxs-lookup"><span data-stu-id="fa92d-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fa92d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="fa92d-112">Requirements</span></span>  
 <span data-ttu-id="fa92d-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fa92d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa92d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="fa92d-114">See also</span></span>

- [<span data-ttu-id="fa92d-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="fa92d-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="fa92d-116">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="fa92d-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
