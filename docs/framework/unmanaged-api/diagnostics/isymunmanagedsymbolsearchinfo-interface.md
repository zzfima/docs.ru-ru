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
ms.openlocfilehash: d573264bb7a3cac02dd41afacaa2bc4a6f9e6dcd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944575"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="5a939-102">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="5a939-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="5a939-103">Предоставляет методы, которые получают сведения о пути поиска.</span><span class="sxs-lookup"><span data-stu-id="5a939-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="5a939-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5a939-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a939-105">Методы</span><span class="sxs-lookup"><span data-stu-id="5a939-105">Methods</span></span>  
  
|<span data-ttu-id="5a939-106">Метод</span><span class="sxs-lookup"><span data-stu-id="5a939-106">Method</span></span>|<span data-ttu-id="5a939-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5a939-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a939-108">Метод GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="5a939-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="5a939-109">Получает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="5a939-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="5a939-110">Метод GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="5a939-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="5a939-111">Получает пути поиска.</span><span class="sxs-lookup"><span data-stu-id="5a939-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="5a939-112">Метод GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="5a939-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="5a939-113">Получает длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="5a939-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a939-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5a939-114">Requirements</span></span>  
 <span data-ttu-id="5a939-115">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5a939-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a939-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5a939-116">See also</span></span>

- [<span data-ttu-id="5a939-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="5a939-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
