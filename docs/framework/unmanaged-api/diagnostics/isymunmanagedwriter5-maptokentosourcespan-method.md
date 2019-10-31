---
title: Метод ISymUnmanagedWriter5::MapTokenToSourceSpan
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: 876804e7b825443116b1f44a02a685a73153915c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121629"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="04a5b-102">Метод ISymUnmanagedWriter5::MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="04a5b-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="04a5b-103">Сопоставляет заданный токен метаданных с заданным диапазоном исходной строки в указанном исходном файле.</span><span class="sxs-lookup"><span data-stu-id="04a5b-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="04a5b-104">Должен вызываться между вызовами [метода OpenMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) и [метода CloseMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="04a5b-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04a5b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04a5b-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04a5b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="04a5b-106">Parameters</span></span>  
  
|<span data-ttu-id="04a5b-107">Параметр</span><span class="sxs-lookup"><span data-stu-id="04a5b-107">Parameter</span></span>|<span data-ttu-id="04a5b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="04a5b-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="04a5b-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="04a5b-109">Return Value</span></span>  
 <span data-ttu-id="04a5b-110">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="04a5b-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04a5b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="04a5b-111">Requirements</span></span>  
 <span data-ttu-id="04a5b-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="04a5b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a5b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="04a5b-113">See also</span></span>

- [<span data-ttu-id="04a5b-114">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="04a5b-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
