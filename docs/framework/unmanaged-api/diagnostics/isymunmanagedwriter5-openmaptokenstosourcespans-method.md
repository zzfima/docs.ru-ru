---
title: Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 004e1ddae8a6c0262846422a2eeb4314a4c82f65
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121615"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="212eb-102">Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="212eb-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="212eb-103">Откройте Специальный раздел настраиваемых данных, чтобы выдать сведения о сопоставлении диапазона от токена к источнику в.</span><span class="sxs-lookup"><span data-stu-id="212eb-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="212eb-104">Открытие этого раздела, если метод уже открыт или наоборот, является ошибкой.</span><span class="sxs-lookup"><span data-stu-id="212eb-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="212eb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="212eb-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="212eb-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="212eb-106">Return Value</span></span>  
 <span data-ttu-id="212eb-107">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="212eb-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="212eb-108">Требования</span><span class="sxs-lookup"><span data-stu-id="212eb-108">Requirements</span></span>  
 <span data-ttu-id="212eb-109">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="212eb-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="212eb-110">См. также</span><span class="sxs-lookup"><span data-stu-id="212eb-110">See also</span></span>

- [<span data-ttu-id="212eb-111">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="212eb-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
