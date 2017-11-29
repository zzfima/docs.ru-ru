---
title: "Интерфейс ISymUnmanagedWriter2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2
helpviewer_keywords: ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bd297a8ee0172f1624e6983de9bc9bf25bd86621
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="f9afb-102">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="f9afb-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="f9afb-103">Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные.</span><span class="sxs-lookup"><span data-stu-id="f9afb-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="f9afb-104">Этот интерфейс расширяет интерфейс [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f9afb-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f9afb-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f9afb-105">Methods</span></span>  
  
|<span data-ttu-id="f9afb-106">Метод</span><span class="sxs-lookup"><span data-stu-id="f9afb-106">Method</span></span>|<span data-ttu-id="f9afb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f9afb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f9afb-108">Метод DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="f9afb-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="f9afb-109">Определяет имя для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="f9afb-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="f9afb-110">Метод DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="f9afb-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="f9afb-111">Определяет одну глобальную переменную.</span><span class="sxs-lookup"><span data-stu-id="f9afb-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="f9afb-112">Метод DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="f9afb-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="f9afb-113">Определяет одну переменную в текущей лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="f9afb-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9afb-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f9afb-114">Requirements</span></span>  
 <span data-ttu-id="f9afb-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f9afb-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9afb-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f9afb-116">See Also</span></span>  
 [<span data-ttu-id="f9afb-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="f9afb-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="f9afb-118">ISymUnmanagedWriter-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f9afb-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="f9afb-119">Isymunmanagedwriter3-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f9afb-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
