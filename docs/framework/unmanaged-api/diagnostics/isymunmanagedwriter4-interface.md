---
title: Интерфейс ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e8478aed662142b9ff4b73f9cb192f8d2306e2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="f4542-102">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="f4542-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="f4542-103">Интерфейс ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="f4542-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4542-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4542-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="f4542-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f4542-105">Methods</span></span>  
 <span data-ttu-id="f4542-106">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="f4542-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="f4542-107">Метод</span><span class="sxs-lookup"><span data-stu-id="f4542-107">Method</span></span>|<span data-ttu-id="f4542-108">Описание</span><span class="sxs-lookup"><span data-stu-id="f4542-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4542-109">Метод GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="f4542-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="f4542-110">Работает так же, как [метод GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) за исключением того что строка пути дополняется следующие завершающий символ null, чтобы сделать данные строки фиксированный размер `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="f4542-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="f4542-111">Заполнение предоставляется только в том случае, если длина строки пути, сам меньше, чем `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="f4542-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="f4542-112">Это упрощает для записи этого файла различий PE средства.</span><span class="sxs-lookup"><span data-stu-id="f4542-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4542-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f4542-113">Requirements</span></span>  
 <span data-ttu-id="f4542-114">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f4542-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4542-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f4542-115">See Also</span></span>  
 [<span data-ttu-id="f4542-116">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="f4542-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="f4542-117">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="f4542-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
