---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d000e61736f3250c677014cce50a2b7dcdecf1b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491691"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="40519-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="40519-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="40519-103">Задает смещение для обработчика catch, созданный компилятором, который создает оболочку для асинхронного метода на промежуточном Языке.</span><span class="sxs-lookup"><span data-stu-id="40519-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="40519-104">Смещение на промежуточном Языке создаваемый catch используется отладчиком для обработки catch, как если бы не написанный пользователем код, несмотря на то, что он может возникнуть в коде пользовательского метода.</span><span class="sxs-lookup"><span data-stu-id="40519-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="40519-105">В частности, он используется в ответ на **CatchHandlerFound** события исключения.</span><span class="sxs-lookup"><span data-stu-id="40519-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40519-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40519-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40519-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="40519-107">Parameters</span></span>  
  
|<span data-ttu-id="40519-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="40519-108">Parameter</span></span>|<span data-ttu-id="40519-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="40519-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="40519-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="40519-110">Return Value</span></span>  
 <span data-ttu-id="40519-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="40519-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40519-112">Требования</span><span class="sxs-lookup"><span data-stu-id="40519-112">Requirements</span></span>  
 <span data-ttu-id="40519-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="40519-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40519-114">См. также</span><span class="sxs-lookup"><span data-stu-id="40519-114">See also</span></span>
- [<span data-ttu-id="40519-115">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="40519-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
