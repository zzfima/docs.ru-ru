---
title: "Интерфейс ISymUnmanagedNamespace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedNamespace
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedNamespace
helpviewer_keywords: ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: d42bea4e-5848-4e43-a883-69af7a313ce9
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1acca300362162b94410aadb10b123b4ecacc664
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagednamespace-interface"></a><span data-ttu-id="d7c1a-102">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="d7c1a-102">ISymUnmanagedNamespace Interface</span></span>
<span data-ttu-id="d7c1a-103">Представляет пространство имен.</span><span class="sxs-lookup"><span data-stu-id="d7c1a-103">Represents a namespace.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7c1a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d7c1a-104">Methods</span></span>  
  
|<span data-ttu-id="d7c1a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d7c1a-105">Method</span></span>|<span data-ttu-id="d7c1a-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="d7c1a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7c1a-107">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="d7c1a-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getname-method.md)|<span data-ttu-id="d7c1a-108">Возвращает имя этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d7c1a-108">Gets the name of this namespace.</span></span>|  
|[<span data-ttu-id="d7c1a-109">Метод GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="d7c1a-109">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getnamespaces-method.md)|<span data-ttu-id="d7c1a-110">Возвращает дочерние элементы этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d7c1a-110">Gets the children of this namespace.</span></span>|  
|[<span data-ttu-id="d7c1a-111">Метод GetVariables</span><span class="sxs-lookup"><span data-stu-id="d7c1a-111">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getvariables-method.md)|<span data-ttu-id="d7c1a-112">Возвращает все переменные, определенные в глобальной области видимости в пределах этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d7c1a-112">Returns all variables defined at global scope within this namespace.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7c1a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d7c1a-113">Requirements</span></span>  
 <span data-ttu-id="d7c1a-114">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d7c1a-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7c1a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d7c1a-115">See Also</span></span>  
 [<span data-ttu-id="d7c1a-116">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="d7c1a-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
