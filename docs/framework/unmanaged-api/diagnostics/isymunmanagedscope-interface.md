---
title: Интерфейс ISymUnmanagedScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: 8da4da38d23ed65a0fdc44a0f919ee8cad2fe18e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446267"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="434f9-102">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="434f9-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="434f9-103">Represents a lexical scope within a method.</span><span class="sxs-lookup"><span data-stu-id="434f9-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="434f9-104">Методы</span><span class="sxs-lookup"><span data-stu-id="434f9-104">Methods</span></span>  
  
|<span data-ttu-id="434f9-105">Метод</span><span class="sxs-lookup"><span data-stu-id="434f9-105">Method</span></span>|<span data-ttu-id="434f9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="434f9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="434f9-107">Метод GetChildren</span><span class="sxs-lookup"><span data-stu-id="434f9-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="434f9-108">Gets the children of this scope.</span><span class="sxs-lookup"><span data-stu-id="434f9-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="434f9-109">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="434f9-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="434f9-110">Gets the end offset for this scope.</span><span class="sxs-lookup"><span data-stu-id="434f9-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="434f9-111">Метод GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="434f9-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="434f9-112">Gets a count of the local variables defined within this scope.</span><span class="sxs-lookup"><span data-stu-id="434f9-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="434f9-113">Метод GetLocals</span><span class="sxs-lookup"><span data-stu-id="434f9-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="434f9-114">Gets the local variables defined within this scope.</span><span class="sxs-lookup"><span data-stu-id="434f9-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="434f9-115">Метод GetMethod</span><span class="sxs-lookup"><span data-stu-id="434f9-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="434f9-116">Gets the method that contains this scope.</span><span class="sxs-lookup"><span data-stu-id="434f9-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="434f9-117">Метод GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="434f9-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="434f9-118">Gets the namespaces that are being used within this scope.</span><span class="sxs-lookup"><span data-stu-id="434f9-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="434f9-119">Метод GetParent</span><span class="sxs-lookup"><span data-stu-id="434f9-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="434f9-120">Gets the parent scope of this scope.</span><span class="sxs-lookup"><span data-stu-id="434f9-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="434f9-121">Метод GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="434f9-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="434f9-122">Gets the start offset for this scope.</span><span class="sxs-lookup"><span data-stu-id="434f9-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="434f9-123">Требования</span><span class="sxs-lookup"><span data-stu-id="434f9-123">Requirements</span></span>  
 <span data-ttu-id="434f9-124">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="434f9-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="434f9-125">См. также</span><span class="sxs-lookup"><span data-stu-id="434f9-125">See also</span></span>

- [<span data-ttu-id="434f9-126">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="434f9-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="434f9-127">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="434f9-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
