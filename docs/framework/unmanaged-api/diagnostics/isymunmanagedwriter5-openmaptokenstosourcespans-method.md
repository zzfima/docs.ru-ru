---
title: Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82dc2ced988f7277c994eb9449e7c26efa5450b7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222683"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="65ac3-102">Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="65ac3-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="65ac3-103">Откройте раздел специальные пользовательские данные для отправки сопоставления диапазона маркера к источнику данных в.</span><span class="sxs-lookup"><span data-stu-id="65ac3-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="65ac3-104">Когда метод уже открыт, или наоборот, является ошибкой при открытии в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="65ac3-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65ac3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65ac3-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="65ac3-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="65ac3-106">Return Value</span></span>  
 <span data-ttu-id="65ac3-107">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="65ac3-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65ac3-108">Требования</span><span class="sxs-lookup"><span data-stu-id="65ac3-108">Requirements</span></span>  
 <span data-ttu-id="65ac3-109">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="65ac3-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65ac3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="65ac3-110">See also</span></span>

- [<span data-ttu-id="65ac3-111">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="65ac3-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
