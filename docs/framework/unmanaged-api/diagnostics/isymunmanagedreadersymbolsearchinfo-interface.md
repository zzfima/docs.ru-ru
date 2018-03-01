---
title: "Интерфейс ISymUnmanagedReaderSymbolSearchInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedReaderSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedReaderSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: fde7e21d-1169-4bed-a34d-792e69652bf9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a7f53e45eb321f114483648afc63d2669065a791
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="455bf-102">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="455bf-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="455bf-103">Предоставляет методы, получающие сведения о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="455bf-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="455bf-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий интерфейс [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="455bf-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="455bf-105">Методы</span><span class="sxs-lookup"><span data-stu-id="455bf-105">Methods</span></span>  
  
|<span data-ttu-id="455bf-106">Метод</span><span class="sxs-lookup"><span data-stu-id="455bf-106">Method</span></span>|<span data-ttu-id="455bf-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="455bf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="455bf-108">Метод GetSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="455bf-108">GetSymbolSearchInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="455bf-109">Возвращает сведения о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="455bf-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="455bf-110">Метод GetSymbolSearchInfoCount</span><span class="sxs-lookup"><span data-stu-id="455bf-110">GetSymbolSearchInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="455bf-111">Возвращает количество сведений для поиска символов.</span><span class="sxs-lookup"><span data-stu-id="455bf-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="455bf-112">Требования</span><span class="sxs-lookup"><span data-stu-id="455bf-112">Requirements</span></span>  
 <span data-ttu-id="455bf-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="455bf-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="455bf-114">См. также</span><span class="sxs-lookup"><span data-stu-id="455bf-114">See Also</span></span>  
 [<span data-ttu-id="455bf-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="455bf-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
