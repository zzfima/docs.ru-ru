---
title: "Интерфейс ISymUnmanagedScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope
helpviewer_keywords: ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d25d62dd42e3e93124c9a3bd8945be265f192663
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="f3f06-102">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="f3f06-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="f3f06-103">Представляет лексическую область видимости в пределах одного метода.</span><span class="sxs-lookup"><span data-stu-id="f3f06-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3f06-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f3f06-104">Methods</span></span>  
  
|<span data-ttu-id="f3f06-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f3f06-105">Method</span></span>|<span data-ttu-id="f3f06-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f3f06-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3f06-107">Метод GetChildren</span><span class="sxs-lookup"><span data-stu-id="f3f06-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="f3f06-108">Получает дочерний объект этой области.</span><span class="sxs-lookup"><span data-stu-id="f3f06-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="f3f06-109">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="f3f06-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="f3f06-110">Возвращает конечное смещение для этой области.</span><span class="sxs-lookup"><span data-stu-id="f3f06-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="f3f06-111">Метод GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="f3f06-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="f3f06-112">Возвращает количество локальных переменных, определенных в данной области.</span><span class="sxs-lookup"><span data-stu-id="f3f06-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="f3f06-113">Метод GetLocals</span><span class="sxs-lookup"><span data-stu-id="f3f06-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="f3f06-114">Возвращает локальные переменные, определенные в этой области.</span><span class="sxs-lookup"><span data-stu-id="f3f06-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="f3f06-115">Метод GetMethod</span><span class="sxs-lookup"><span data-stu-id="f3f06-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="f3f06-116">Возвращает метод, содержащий эту область.</span><span class="sxs-lookup"><span data-stu-id="f3f06-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="f3f06-117">Getnamespaces-метод</span><span class="sxs-lookup"><span data-stu-id="f3f06-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="f3f06-118">Возвращает пространства имен, используемые в этой области.</span><span class="sxs-lookup"><span data-stu-id="f3f06-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="f3f06-119">Метод GetParent</span><span class="sxs-lookup"><span data-stu-id="f3f06-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="f3f06-120">Возвращает область родительской области.</span><span class="sxs-lookup"><span data-stu-id="f3f06-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="f3f06-121">Метод GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="f3f06-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="f3f06-122">Возвращает начальное смещение для этой области.</span><span class="sxs-lookup"><span data-stu-id="f3f06-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3f06-123">Требования</span><span class="sxs-lookup"><span data-stu-id="f3f06-123">Requirements</span></span>  
 <span data-ttu-id="f3f06-124">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f3f06-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3f06-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f3f06-125">See Also</span></span>  
 [<span data-ttu-id="f3f06-126">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="f3f06-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="f3f06-127">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="f3f06-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
