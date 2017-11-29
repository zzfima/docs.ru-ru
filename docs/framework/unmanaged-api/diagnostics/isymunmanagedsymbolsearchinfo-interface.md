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
ms.openlocfilehash: 967511238dceb752ab30ce10dcaba8b65f4dd9fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="23ae7-102">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="23ae7-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="23ae7-103">Предоставляет методы, получающие сведения о пути поиска.</span><span class="sxs-lookup"><span data-stu-id="23ae7-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="23ae7-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий интерфейс [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="23ae7-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23ae7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="23ae7-105">Methods</span></span>  
  
|<span data-ttu-id="23ae7-106">Метод</span><span class="sxs-lookup"><span data-stu-id="23ae7-106">Method</span></span>|<span data-ttu-id="23ae7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="23ae7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23ae7-108">Метод GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="23ae7-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="23ae7-109">Возвращает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="23ae7-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="23ae7-110">Метод GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="23ae7-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="23ae7-111">Получает пути поиска.</span><span class="sxs-lookup"><span data-stu-id="23ae7-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="23ae7-112">Метод GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="23ae7-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="23ae7-113">Получает длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="23ae7-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23ae7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="23ae7-114">Requirements</span></span>  
 <span data-ttu-id="23ae7-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="23ae7-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23ae7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="23ae7-116">See Also</span></span>  
 [<span data-ttu-id="23ae7-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="23ae7-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
