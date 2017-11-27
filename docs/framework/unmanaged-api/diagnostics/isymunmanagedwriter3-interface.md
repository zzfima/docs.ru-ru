---
title: "Интерфейс ISymUnmanagedWriter3"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter3
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter3
helpviewer_keywords: ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3babf8b3a54f07ac4eb14e326f66c70834953dfe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="2ec0c-102">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="2ec0c-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="2ec0c-103">Представляет модуль записи символов и предоставляет методы для определения документов, точек следования, лексические области и переменные.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="2ec0c-104">Этот интерфейс расширяет интерфейс [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ec0c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="2ec0c-105">Methods</span></span>  
  
|<span data-ttu-id="2ec0c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="2ec0c-106">Method</span></span>|<span data-ttu-id="2ec0c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2ec0c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ec0c-108">Метод Commit</span><span class="sxs-lookup"><span data-stu-id="2ec0c-108">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="2ec0c-109">Фиксирует изменения, записанных в поток.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="2ec0c-110">Метод OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="2ec0c-110">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="2ec0c-111">Открывает метод и предоставляет его фактическое смещение раздела в образе.</span><span class="sxs-lookup"><span data-stu-id="2ec0c-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ec0c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2ec0c-112">Requirements</span></span>  
 <span data-ttu-id="2ec0c-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2ec0c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec0c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2ec0c-114">See Also</span></span>  
 [<span data-ttu-id="2ec0c-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="2ec0c-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="2ec0c-116">ISymUnmanagedWriter-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2ec0c-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="2ec0c-117">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="2ec0c-117">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
