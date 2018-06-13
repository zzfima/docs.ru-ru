---
title: Интерфейс ISymUnmanagedSourceServerModule
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule
helpviewer_keywords:
- ISymUnmanagedSourceServerModule interface [.NET Framework debugging]
ms.assetid: a19b23bd-2061-476e-b67d-252f57404f8b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a63700abf77d56134ca30620033c398af735599
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426743"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="8645d-102">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="8645d-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="8645d-103">Предоставляет данные сервера источника для модуля.</span><span class="sxs-lookup"><span data-stu-id="8645d-103">Provides source server data for a module.</span></span> <span data-ttu-id="8645d-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий интерфейс [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8645d-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8645d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8645d-105">Methods</span></span>  
  
|<span data-ttu-id="8645d-106">Метод</span><span class="sxs-lookup"><span data-stu-id="8645d-106">Method</span></span>|<span data-ttu-id="8645d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8645d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8645d-108">Метод GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="8645d-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="8645d-109">Возвращает данные исходного сервера для модуля.</span><span class="sxs-lookup"><span data-stu-id="8645d-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8645d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8645d-110">Requirements</span></span>  
 <span data-ttu-id="8645d-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8645d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8645d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8645d-112">See Also</span></span>  
 [<span data-ttu-id="8645d-113">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="8645d-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
