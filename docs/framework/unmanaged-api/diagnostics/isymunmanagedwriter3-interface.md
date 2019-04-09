---
title: Интерфейс ISymUnmanagedWriter3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e26d79a5b597b8585f2fffd7f3945f00832ca134
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138460"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="1a151-102">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="1a151-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="1a151-103">Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные.</span><span class="sxs-lookup"><span data-stu-id="1a151-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="1a151-104">Этот интерфейс расширяет [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1a151-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1a151-105">Методы</span><span class="sxs-lookup"><span data-stu-id="1a151-105">Methods</span></span>  
  
|<span data-ttu-id="1a151-106">Метод</span><span class="sxs-lookup"><span data-stu-id="1a151-106">Method</span></span>|<span data-ttu-id="1a151-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1a151-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1a151-108">Метод Commit</span><span class="sxs-lookup"><span data-stu-id="1a151-108">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="1a151-109">Фиксирует изменения, записанных в поток.</span><span class="sxs-lookup"><span data-stu-id="1a151-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="1a151-110">Метод OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="1a151-110">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="1a151-111">Открывает метод и предоставляет его фактическое смещение раздела в образе.</span><span class="sxs-lookup"><span data-stu-id="1a151-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a151-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1a151-112">Requirements</span></span>  
 <span data-ttu-id="1a151-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1a151-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a151-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1a151-114">See also</span></span>

- [<span data-ttu-id="1a151-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="1a151-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="1a151-116">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="1a151-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="1a151-117">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="1a151-117">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
