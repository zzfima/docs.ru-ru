---
title: Интерфейс ISymUnmanagedReaderSymbolSearchInfo
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a6eb99de44c2d3f1afe6dda2d6ec895ec57c617
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635013"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="64c6e-102">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="64c6e-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="64c6e-103">Предоставляет методы, получающие сведения о поиске символа.</span><span class="sxs-lookup"><span data-stu-id="64c6e-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="64c6e-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="64c6e-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="64c6e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="64c6e-105">Methods</span></span>  
  
|<span data-ttu-id="64c6e-106">Метод</span><span class="sxs-lookup"><span data-stu-id="64c6e-106">Method</span></span>|<span data-ttu-id="64c6e-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="64c6e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="64c6e-108">Метод GetSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="64c6e-108">GetSymbolSearchInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="64c6e-109">Возвращает сведения о поиске символа.</span><span class="sxs-lookup"><span data-stu-id="64c6e-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="64c6e-110">Метод GetSymbolSearchInfoCount</span><span class="sxs-lookup"><span data-stu-id="64c6e-110">GetSymbolSearchInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="64c6e-111">Возвращает счетчик для поиска символьной информации.</span><span class="sxs-lookup"><span data-stu-id="64c6e-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="64c6e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="64c6e-112">Requirements</span></span>  
 <span data-ttu-id="64c6e-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="64c6e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64c6e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="64c6e-114">See also</span></span>
- [<span data-ttu-id="64c6e-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="64c6e-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
