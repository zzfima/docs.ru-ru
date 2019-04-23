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
ms.openlocfilehash: 2a872774b1c4510c8d0325c59ae7678c867c1aff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216812"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="5e3f8-102">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="5e3f8-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="5e3f8-103">Предоставляет методы, получающие сведения о поиске символа.</span><span class="sxs-lookup"><span data-stu-id="5e3f8-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="5e3f8-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5e3f8-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e3f8-105">Методы</span><span class="sxs-lookup"><span data-stu-id="5e3f8-105">Methods</span></span>  
  
|<span data-ttu-id="5e3f8-106">Метод</span><span class="sxs-lookup"><span data-stu-id="5e3f8-106">Method</span></span>|<span data-ttu-id="5e3f8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5e3f8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e3f8-108">Метод GetSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="5e3f8-108">GetSymbolSearchInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="5e3f8-109">Возвращает сведения о поиске символа.</span><span class="sxs-lookup"><span data-stu-id="5e3f8-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="5e3f8-110">Метод GetSymbolSearchInfoCount</span><span class="sxs-lookup"><span data-stu-id="5e3f8-110">GetSymbolSearchInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="5e3f8-111">Возвращает счетчик для поиска символьной информации.</span><span class="sxs-lookup"><span data-stu-id="5e3f8-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e3f8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5e3f8-112">Requirements</span></span>  
 <span data-ttu-id="5e3f8-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5e3f8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e3f8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5e3f8-114">See also</span></span>

- [<span data-ttu-id="5e3f8-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="5e3f8-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
