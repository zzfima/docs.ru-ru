---
title: Интерфейс ISymUnmanagedWriter5
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6ed8c6e61c558a4bc9e3f92d559615ac93ecff8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144239"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="bfeaf-102">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="bfeaf-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="bfeaf-103">Интерфейс ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="bfeaf-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfeaf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfeaf-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="bfeaf-105">Методы</span><span class="sxs-lookup"><span data-stu-id="bfeaf-105">Methods</span></span>  
 <span data-ttu-id="bfeaf-106">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="bfeaf-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="bfeaf-107">Метод</span><span class="sxs-lookup"><span data-stu-id="bfeaf-107">Method</span></span>|<span data-ttu-id="bfeaf-108">Описание</span><span class="sxs-lookup"><span data-stu-id="bfeaf-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bfeaf-109">Метод CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="bfeaf-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="bfeaf-110">Закройте раздел специальные пользовательские данные для маркера в исходный диапазон, сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="bfeaf-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="bfeaf-111">После его закрытия можно добавить нет Дополнительные сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="bfeaf-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="bfeaf-112">Метод MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="bfeaf-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="bfeaf-113">Maps маркер заданных метаданных для заданной строки исходного диапазона в указанный исходный файл.</span><span class="sxs-lookup"><span data-stu-id="bfeaf-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="bfeaf-114">Должен вызываться между вызовами [метод OpenMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) и [метод CloseMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="bfeaf-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="bfeaf-115">Метод OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="bfeaf-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="bfeaf-116">Откройте раздел специальные пользовательские данные для отправки сопоставления диапазона маркера к источнику данных в.</span><span class="sxs-lookup"><span data-stu-id="bfeaf-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="bfeaf-117">Когда метод уже открыт, или наоборот, является ошибкой при открытии в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bfeaf-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bfeaf-118">Требования</span><span class="sxs-lookup"><span data-stu-id="bfeaf-118">Requirements</span></span>  
 <span data-ttu-id="bfeaf-119">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bfeaf-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfeaf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="bfeaf-120">See also</span></span>

- [<span data-ttu-id="bfeaf-121">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="bfeaf-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="bfeaf-122">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="bfeaf-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
