---
title: Интерфейс ISymUnmanagedWriter5
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: 18371b6aefb002f5adf27d43f85194c6c35f6ef5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121644"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="4dfe7-102">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="4dfe7-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="4dfe7-103">Интерфейс ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dfe7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4dfe7-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="4dfe7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4dfe7-105">Methods</span></span>  
 <span data-ttu-id="4dfe7-106">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="4dfe7-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="4dfe7-107">Метод</span><span class="sxs-lookup"><span data-stu-id="4dfe7-107">Method</span></span>|<span data-ttu-id="4dfe7-108">Описание</span><span class="sxs-lookup"><span data-stu-id="4dfe7-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4dfe7-109">Метод CloseMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="4dfe7-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="4dfe7-110">Закройте Специальный раздел настраиваемых данных, чтобы получить сведения о сопоставлении диапазона "токен-источник".</span><span class="sxs-lookup"><span data-stu-id="4dfe7-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="4dfe7-111">После закрытия не удается добавить дополнительные сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="4dfe7-112">Метод MapTokenToSourceSpan</span><span class="sxs-lookup"><span data-stu-id="4dfe7-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="4dfe7-113">Сопоставляет заданный токен метаданных с заданным диапазоном исходной строки в указанном исходном файле.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="4dfe7-114">Должен вызываться между вызовами [метода OpenMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) и [метода CloseMapTokensToSourceSpans](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="4dfe7-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="4dfe7-115">Метод OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="4dfe7-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="4dfe7-116">Откройте Специальный раздел настраиваемых данных, чтобы выдать сведения о сопоставлении диапазона от токена к источнику в.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="4dfe7-117">Открытие этого раздела, если метод уже открыт или наоборот, является ошибкой.</span><span class="sxs-lookup"><span data-stu-id="4dfe7-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4dfe7-118">Требования</span><span class="sxs-lookup"><span data-stu-id="4dfe7-118">Requirements</span></span>  
 <span data-ttu-id="4dfe7-119">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="4dfe7-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dfe7-120">См. также</span><span class="sxs-lookup"><span data-stu-id="4dfe7-120">See also</span></span>

- [<span data-ttu-id="4dfe7-121">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="4dfe7-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="4dfe7-122">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="4dfe7-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
