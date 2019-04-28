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
ms.openlocfilehash: 3ba81c208c4b49342c6a055e09ba898871db1851
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922139"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="68d08-102">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="68d08-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="68d08-103">Предоставляет данные исходного сервера для модуля.</span><span class="sxs-lookup"><span data-stu-id="68d08-103">Provides source server data for a module.</span></span> <span data-ttu-id="68d08-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="68d08-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="68d08-105">Методы</span><span class="sxs-lookup"><span data-stu-id="68d08-105">Methods</span></span>  
  
|<span data-ttu-id="68d08-106">Метод</span><span class="sxs-lookup"><span data-stu-id="68d08-106">Method</span></span>|<span data-ttu-id="68d08-107">Описание</span><span class="sxs-lookup"><span data-stu-id="68d08-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68d08-108">Метод GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="68d08-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="68d08-109">Возвращает данные исходного сервера для модуля.</span><span class="sxs-lookup"><span data-stu-id="68d08-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68d08-110">Требования</span><span class="sxs-lookup"><span data-stu-id="68d08-110">Requirements</span></span>  
 <span data-ttu-id="68d08-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="68d08-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d08-112">См. также</span><span class="sxs-lookup"><span data-stu-id="68d08-112">See also</span></span>

- [<span data-ttu-id="68d08-113">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="68d08-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
