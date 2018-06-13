---
title: Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d3bc8b00b568f96cd55b7811f310d34c1ff700d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428652"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="b7015-102">Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="b7015-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="b7015-103">Откройте раздел специальные пользовательские данные для передачи сведений о сопоставлении span токен источника в.</span><span class="sxs-lookup"><span data-stu-id="b7015-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="b7015-104">Когда метод уже открыт, или наоборот, возникает ошибка при открытии в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b7015-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7015-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7015-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b7015-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b7015-106">Return Value</span></span>  
 <span data-ttu-id="b7015-107">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="b7015-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7015-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b7015-108">Requirements</span></span>  
 <span data-ttu-id="b7015-109">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b7015-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7015-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b7015-110">See Also</span></span>  
 [<span data-ttu-id="b7015-111">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="b7015-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
