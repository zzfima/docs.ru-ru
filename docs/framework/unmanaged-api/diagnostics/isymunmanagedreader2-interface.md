---
title: "Интерфейс ISymUnmanagedReader2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2
helpviewer_keywords: ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b23e166249659b94d454070c01c003495d1018a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="83b7d-102">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="83b7d-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="83b7d-103">Представляет средство чтения символов, который предоставляет доступ к документам, методам и переменным в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="83b7d-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="83b7d-104">Этот интерфейс расширяет интерфейс [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="83b7d-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83b7d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="83b7d-105">Methods</span></span>  
  
|<span data-ttu-id="83b7d-106">Метод</span><span class="sxs-lookup"><span data-stu-id="83b7d-106">Method</span></span>|<span data-ttu-id="83b7d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="83b7d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83b7d-108">Метод GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="83b7d-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="83b7d-109">Получение метода средства чтения символов, заданному маркеру метода и номеру версии edit-and-continue.</span><span class="sxs-lookup"><span data-stu-id="83b7d-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="83b7d-110">Метод GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="83b7d-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="83b7d-111">Возвращает каждого метода, который содержит сведения о строке в указанный документ.</span><span class="sxs-lookup"><span data-stu-id="83b7d-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="83b7d-112">Метод GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="83b7d-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="83b7d-113">Получает пользовательский атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="83b7d-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83b7d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="83b7d-114">Requirements</span></span>  
 <span data-ttu-id="83b7d-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="83b7d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b7d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="83b7d-116">See Also</span></span>  
 [<span data-ttu-id="83b7d-117">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="83b7d-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="83b7d-118">ISymUnmanagedReader-интерфейс</span><span class="sxs-lookup"><span data-stu-id="83b7d-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
