---
title: "Метод ISymUnmanagedWriter5::CloseMapTokensToSourceSpans"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f8a0c0a2-a11d-436c-aa85-bc110215cfd6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2f8a89532999f599c8ec595fa709044b7d13a53a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter5closemaptokenstosourcespans-method"></a><span data-ttu-id="45868-102">Метод ISymUnmanagedWriter5::CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="45868-102">ISymUnmanagedWriter5::CloseMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="45868-103">Закройте раздел специальных пользовательских данных для маркера в исходный диапазон, сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="45868-103">Close the special custom data section for token-to-source span mapping information.</span></span> <span data-ttu-id="45868-104">После его закрытия можно добавить нет Дополнительные сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="45868-104">After it is closed, no more mapping information can be added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45868-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45868-105">Syntax</span></span>  
  
```idl  
HRESULT CloseMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="45868-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="45868-106">Return Value</span></span>  
 <span data-ttu-id="45868-107">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="45868-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45868-108">Требования</span><span class="sxs-lookup"><span data-stu-id="45868-108">Requirements</span></span>  
 <span data-ttu-id="45868-109">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="45868-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45868-110">См. также</span><span class="sxs-lookup"><span data-stu-id="45868-110">See Also</span></span>  
 [<span data-ttu-id="45868-111">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="45868-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
