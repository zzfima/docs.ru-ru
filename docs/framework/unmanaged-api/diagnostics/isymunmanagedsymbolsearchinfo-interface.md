---
title: Интерфейс ISymUnmanagedSymbolSearchInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f5fc951b629a3158fc2c2d6047234fb661f3741
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494903"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="1bebe-102">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="1bebe-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="1bebe-103">Предоставляет методы, которые получают сведения о пути поиска.</span><span class="sxs-lookup"><span data-stu-id="1bebe-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="1bebe-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1bebe-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1bebe-105">Методы</span><span class="sxs-lookup"><span data-stu-id="1bebe-105">Methods</span></span>  
  
|<span data-ttu-id="1bebe-106">Метод</span><span class="sxs-lookup"><span data-stu-id="1bebe-106">Method</span></span>|<span data-ttu-id="1bebe-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="1bebe-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1bebe-108">Метод GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="1bebe-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="1bebe-109">Получает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="1bebe-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="1bebe-110">Метод GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="1bebe-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="1bebe-111">Получает пути поиска.</span><span class="sxs-lookup"><span data-stu-id="1bebe-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="1bebe-112">Метод GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="1bebe-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="1bebe-113">Получает длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="1bebe-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1bebe-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1bebe-114">Requirements</span></span>  
 <span data-ttu-id="1bebe-115">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1bebe-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bebe-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1bebe-116">See also</span></span>
- [<span data-ttu-id="1bebe-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="1bebe-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
