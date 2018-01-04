---
title: "Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cb283198de5621748b37fe8e22f2fbc408754ad6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="7d7f7-102">Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="7d7f7-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="7d7f7-103">Откройте раздел специальные пользовательские данные для передачи сведений о сопоставлении span токен источника в.</span><span class="sxs-lookup"><span data-stu-id="7d7f7-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="7d7f7-104">Когда метод уже открыт, или наоборот, возникает ошибка при открытии в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7d7f7-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d7f7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d7f7-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7d7f7-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7d7f7-106">Return Value</span></span>  
 <span data-ttu-id="7d7f7-107">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="7d7f7-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d7f7-108">Требования</span><span class="sxs-lookup"><span data-stu-id="7d7f7-108">Requirements</span></span>  
 <span data-ttu-id="7d7f7-109">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7d7f7-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d7f7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="7d7f7-110">See Also</span></span>  
 [<span data-ttu-id="7d7f7-111">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="7d7f7-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
