---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: b108c8c87d3afdbfacb569ab501274e5c45c2e2e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129188"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="05680-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="05680-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="05680-103">Задает смещение IL для обработчика catch, созданного компилятором, который создает оболочку для асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="05680-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="05680-104">Смещение IL созданного блока catch используется отладчиком для управления перехватом, как если бы он был непользовательским кодом, даже если он может возникнуть в методе пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="05680-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="05680-105">В частности, он используется в ответ на событие исключения **катчхандлерфаунд** .</span><span class="sxs-lookup"><span data-stu-id="05680-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05680-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05680-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05680-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="05680-107">Parameters</span></span>  
  
|<span data-ttu-id="05680-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="05680-108">Parameter</span></span>|<span data-ttu-id="05680-109">Описание</span><span class="sxs-lookup"><span data-stu-id="05680-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="05680-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="05680-110">Return Value</span></span>  
 <span data-ttu-id="05680-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="05680-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05680-112">Требования</span><span class="sxs-lookup"><span data-stu-id="05680-112">Requirements</span></span>  
 <span data-ttu-id="05680-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="05680-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05680-114">См. также</span><span class="sxs-lookup"><span data-stu-id="05680-114">See also</span></span>

- [<span data-ttu-id="05680-115">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="05680-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
