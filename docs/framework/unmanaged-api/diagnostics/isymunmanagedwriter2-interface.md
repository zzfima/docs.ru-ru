---
title: Интерфейс ISymUnmanagedWriter2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cbafe39fffd28a9bfccaa275c9009bc03549cda6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429435"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="9cf05-102">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="9cf05-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="9cf05-103">Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные.</span><span class="sxs-lookup"><span data-stu-id="9cf05-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="9cf05-104">Этот интерфейс расширяет интерфейс [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9cf05-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9cf05-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9cf05-105">Methods</span></span>  
  
|<span data-ttu-id="9cf05-106">Метод</span><span class="sxs-lookup"><span data-stu-id="9cf05-106">Method</span></span>|<span data-ttu-id="9cf05-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9cf05-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9cf05-108">Метод DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="9cf05-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="9cf05-109">Определяет имя для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="9cf05-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="9cf05-110">Метод DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="9cf05-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="9cf05-111">Определяет одну глобальную переменную.</span><span class="sxs-lookup"><span data-stu-id="9cf05-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="9cf05-112">Метод DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="9cf05-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="9cf05-113">Определяет одну переменную в текущей лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="9cf05-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9cf05-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9cf05-114">Requirements</span></span>  
 <span data-ttu-id="9cf05-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9cf05-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf05-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9cf05-116">See Also</span></span>  
 [<span data-ttu-id="9cf05-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="9cf05-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="9cf05-118">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="9cf05-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="9cf05-119">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="9cf05-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
