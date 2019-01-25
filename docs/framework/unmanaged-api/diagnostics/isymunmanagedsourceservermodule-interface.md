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
ms.openlocfilehash: 4fed0fcd806bd410c8a6817447e6fd634237624d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743183"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="f7811-102">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="f7811-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="f7811-103">Предоставляет данные исходного сервера для модуля.</span><span class="sxs-lookup"><span data-stu-id="f7811-103">Provides source server data for a module.</span></span> <span data-ttu-id="f7811-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f7811-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7811-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f7811-105">Methods</span></span>  
  
|<span data-ttu-id="f7811-106">Метод</span><span class="sxs-lookup"><span data-stu-id="f7811-106">Method</span></span>|<span data-ttu-id="f7811-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f7811-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7811-108">Метод GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="f7811-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="f7811-109">Возвращает данные исходного сервера для модуля.</span><span class="sxs-lookup"><span data-stu-id="f7811-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7811-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f7811-110">Requirements</span></span>  
 <span data-ttu-id="f7811-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f7811-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7811-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f7811-112">See also</span></span>
- [<span data-ttu-id="f7811-113">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="f7811-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
