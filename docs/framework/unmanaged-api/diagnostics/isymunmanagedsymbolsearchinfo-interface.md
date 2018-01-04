---
title: "Интерфейс ISymUnmanagedSymbolSearchInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedSymbolSearchInfo
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedSymbolSearchInfo
helpviewer_keywords: ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 441330471906a891646ad55eb73ec25b44800cbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="6825d-102">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="6825d-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="6825d-103">Предоставляет методы, получающие сведения о пути поиска.</span><span class="sxs-lookup"><span data-stu-id="6825d-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="6825d-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий интерфейс [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6825d-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6825d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6825d-105">Methods</span></span>  
  
|<span data-ttu-id="6825d-106">Метод</span><span class="sxs-lookup"><span data-stu-id="6825d-106">Method</span></span>|<span data-ttu-id="6825d-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="6825d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6825d-108">Метод GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="6825d-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="6825d-109">Возвращает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="6825d-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="6825d-110">Метод GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="6825d-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="6825d-111">Получает пути поиска.</span><span class="sxs-lookup"><span data-stu-id="6825d-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="6825d-112">Метод GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="6825d-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="6825d-113">Получает длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="6825d-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6825d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="6825d-114">Requirements</span></span>  
 <span data-ttu-id="6825d-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6825d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6825d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6825d-116">See Also</span></span>  
 [<span data-ttu-id="6825d-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="6825d-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
