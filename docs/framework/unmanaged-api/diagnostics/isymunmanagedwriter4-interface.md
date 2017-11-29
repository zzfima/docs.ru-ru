---
title: "Интерфейс ISymUnmanagedWriter4"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7ab7f06ba280675ca8349500e766364d30f9349
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="dfd10-102">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="dfd10-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="dfd10-103">Интерфейс ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="dfd10-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfd10-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dfd10-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="dfd10-105">Методы</span><span class="sxs-lookup"><span data-stu-id="dfd10-105">Methods</span></span>  
 <span data-ttu-id="dfd10-106">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="dfd10-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="dfd10-107">Метод</span><span class="sxs-lookup"><span data-stu-id="dfd10-107">Method</span></span>|<span data-ttu-id="dfd10-108">Описание</span><span class="sxs-lookup"><span data-stu-id="dfd10-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dfd10-109">Метод GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="dfd10-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="dfd10-110">Работает так же, как [метод GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) за исключением того что строка пути дополняется следующие завершающий символ null, чтобы сделать данные строки фиксированный размер `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="dfd10-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="dfd10-111">Заполнение предоставляется только в том случае, если длина строки пути, сам меньше, чем `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="dfd10-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="dfd10-112">Это упрощает для записи этого файла различий PE средства.</span><span class="sxs-lookup"><span data-stu-id="dfd10-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dfd10-113">Требования</span><span class="sxs-lookup"><span data-stu-id="dfd10-113">Requirements</span></span>  
 <span data-ttu-id="dfd10-114">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dfd10-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfd10-115">См. также</span><span class="sxs-lookup"><span data-stu-id="dfd10-115">See Also</span></span>  
 [<span data-ttu-id="dfd10-116">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="dfd10-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="dfd10-117">Isymunmanagedwriter3-интерфейс</span><span class="sxs-lookup"><span data-stu-id="dfd10-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
