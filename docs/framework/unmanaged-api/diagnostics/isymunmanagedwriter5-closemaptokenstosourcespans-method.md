---
title: Метод ISymUnmanagedWriter5::CloseMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 653dd933066898c1954cfbcc57c0c0493e47b4be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428616"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="0742d-102">Метод ISymUnmanagedWriter5::CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="0742d-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="0742d-103">Закройте раздел специальных пользовательских данных для маркера в исходный диапазон, сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="0742d-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="0742d-104">После его закрытия можно добавить нет Дополнительные сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="0742d-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0742d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0742d-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0742d-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0742d-106">Return Value</span></span>  
 <span data-ttu-id="0742d-107">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="0742d-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0742d-108">Требования</span><span class="sxs-lookup"><span data-stu-id="0742d-108">Requirements</span></span>  
 <span data-ttu-id="0742d-109">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0742d-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0742d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0742d-110">See Also</span></span>  
 [<span data-ttu-id="0742d-111">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="0742d-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
