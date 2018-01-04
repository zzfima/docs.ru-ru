---
title: "Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54cc369b309d1ffe20d0f3e6a2d4ae4e0443c85f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="7bdda-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="7bdda-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="7bdda-103">Задает смещение для обработчика catch, созданный компилятором, являющийся оболочкой для асинхронного метода на промежуточном Языке.</span><span class="sxs-lookup"><span data-stu-id="7bdda-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="7bdda-104">Смещение на промежуточном Языке созданный catch используется отладчиком для обработки catch, как если бы не написанный пользователем, несмотря на то, что она может возникать в метода кода пользователя.</span><span class="sxs-lookup"><span data-stu-id="7bdda-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="7bdda-105">В частности, он используется в ответ на **CatchHandlerFound** события исключения.</span><span class="sxs-lookup"><span data-stu-id="7bdda-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bdda-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bdda-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7bdda-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="7bdda-107">Parameters</span></span>  
  
|<span data-ttu-id="7bdda-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="7bdda-108">Parameter</span></span>|<span data-ttu-id="7bdda-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="7bdda-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="7bdda-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7bdda-110">Return Value</span></span>  
 <span data-ttu-id="7bdda-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="7bdda-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bdda-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7bdda-112">Requirements</span></span>  
 <span data-ttu-id="7bdda-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7bdda-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bdda-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7bdda-114">See Also</span></span>  
 [<span data-ttu-id="7bdda-115">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="7bdda-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
