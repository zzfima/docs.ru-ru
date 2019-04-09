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
ms.openlocfilehash: 97df6d6ec9a446e89eef8a9f8a5e5e8ddc85c0f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127404"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="ee907-102">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="ee907-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="ee907-103">Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные.</span><span class="sxs-lookup"><span data-stu-id="ee907-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="ee907-104">Этот интерфейс расширяет [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ee907-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee907-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ee907-105">Methods</span></span>  
  
|<span data-ttu-id="ee907-106">Метод</span><span class="sxs-lookup"><span data-stu-id="ee907-106">Method</span></span>|<span data-ttu-id="ee907-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ee907-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee907-108">Метод DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="ee907-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="ee907-109">Определяет имя для значения константы.</span><span class="sxs-lookup"><span data-stu-id="ee907-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="ee907-110">Метод DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="ee907-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="ee907-111">Определяет одну глобальную переменную.</span><span class="sxs-lookup"><span data-stu-id="ee907-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="ee907-112">Метод DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="ee907-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="ee907-113">Определяет одну переменную в текущей лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="ee907-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee907-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ee907-114">Requirements</span></span>  
 <span data-ttu-id="ee907-115">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ee907-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee907-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ee907-116">See also</span></span>

- [<span data-ttu-id="ee907-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="ee907-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ee907-118">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="ee907-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="ee907-119">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="ee907-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
