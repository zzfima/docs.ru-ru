---
title: Метод ISymUnmanagedWriter5::CloseMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce4b41854d5d9324169b1873f431ef81c0a4c5be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677923"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="ff917-102">Метод ISymUnmanagedWriter5::CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="ff917-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="ff917-103">Закройте раздел специальные пользовательские данные для маркера в исходный диапазон, сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="ff917-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="ff917-104">После его закрытия можно добавить нет Дополнительные сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="ff917-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff917-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff917-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ff917-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ff917-106">Return Value</span></span>  
 <span data-ttu-id="ff917-107">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="ff917-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff917-108">Требования</span><span class="sxs-lookup"><span data-stu-id="ff917-108">Requirements</span></span>  
 <span data-ttu-id="ff917-109">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ff917-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff917-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ff917-110">See also</span></span>
- [<span data-ttu-id="ff917-111">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="ff917-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
