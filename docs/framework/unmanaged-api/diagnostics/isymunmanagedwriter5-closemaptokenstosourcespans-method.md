---
title: Метод ISymUnmanagedWriter5::CloseMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b3dea6b9710f1ee5ccf8c51261f59b2de026f5e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127781"
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="0c993-102">Метод ISymUnmanagedWriter5::CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="0c993-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="0c993-103">Закройте раздел специальные пользовательские данные для маркера в исходный диапазон, сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="0c993-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="0c993-104">После его закрытия можно добавить нет Дополнительные сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="0c993-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c993-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c993-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0c993-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0c993-106">Return Value</span></span>  
 <span data-ttu-id="0c993-107">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="0c993-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c993-108">Требования</span><span class="sxs-lookup"><span data-stu-id="0c993-108">Requirements</span></span>  
 <span data-ttu-id="0c993-109">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0c993-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c993-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0c993-110">See also</span></span>

- [<span data-ttu-id="0c993-111">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="0c993-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
