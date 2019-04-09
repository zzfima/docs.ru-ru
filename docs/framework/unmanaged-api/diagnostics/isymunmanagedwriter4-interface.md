---
title: Интерфейс ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5732cc08512df25a14cc8ea9dcaa03c56207dde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202050"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="83c9f-102">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="83c9f-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="83c9f-103">Интерфейс ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="83c9f-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c9f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83c9f-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="83c9f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="83c9f-105">Methods</span></span>  
 <span data-ttu-id="83c9f-106">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="83c9f-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="83c9f-107">Метод</span><span class="sxs-lookup"><span data-stu-id="83c9f-107">Method</span></span>|<span data-ttu-id="83c9f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="83c9f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83c9f-109">Метод GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="83c9f-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="83c9f-110">Работает так же, как [метод GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) за исключением того, что строка пути дополняется нулей, завершающий нуль-символ, чтобы сделать строковые данные фиксированный размер `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="83c9f-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="83c9f-111">Заполнение предоставляется только в том случае, если длина строки пути, сам меньше, чем `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="83c9f-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="83c9f-112">Это упрощает для записи этого файла различий PE средства.</span><span class="sxs-lookup"><span data-stu-id="83c9f-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83c9f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="83c9f-113">Requirements</span></span>  
 <span data-ttu-id="83c9f-114">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="83c9f-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c9f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="83c9f-115">See also</span></span>

- [<span data-ttu-id="83c9f-116">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="83c9f-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="83c9f-117">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="83c9f-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
