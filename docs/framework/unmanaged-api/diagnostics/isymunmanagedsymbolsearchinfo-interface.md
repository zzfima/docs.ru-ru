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
ms.openlocfilehash: 5dce9653d3fef534ac6567e36a4c8213e13ab231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429173"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="43f56-102">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="43f56-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="43f56-103">Предоставляет методы, получающие сведения о пути поиска.</span><span class="sxs-lookup"><span data-stu-id="43f56-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="43f56-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий интерфейс [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="43f56-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43f56-105">Методы</span><span class="sxs-lookup"><span data-stu-id="43f56-105">Methods</span></span>  
  
|<span data-ttu-id="43f56-106">Метод</span><span class="sxs-lookup"><span data-stu-id="43f56-106">Method</span></span>|<span data-ttu-id="43f56-107">Описание</span><span class="sxs-lookup"><span data-stu-id="43f56-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43f56-108">Метод GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="43f56-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="43f56-109">Возвращает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="43f56-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="43f56-110">Метод GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="43f56-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="43f56-111">Получает пути поиска.</span><span class="sxs-lookup"><span data-stu-id="43f56-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="43f56-112">Метод GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="43f56-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="43f56-113">Получает длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="43f56-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43f56-114">Требования</span><span class="sxs-lookup"><span data-stu-id="43f56-114">Requirements</span></span>  
 <span data-ttu-id="43f56-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="43f56-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43f56-116">См. также</span><span class="sxs-lookup"><span data-stu-id="43f56-116">See Also</span></span>  
 [<span data-ttu-id="43f56-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="43f56-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
