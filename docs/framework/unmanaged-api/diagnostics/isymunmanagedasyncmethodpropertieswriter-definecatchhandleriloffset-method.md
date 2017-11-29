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
ms.openlocfilehash: 3bae0e2dfb56883a674b282acd385ba45a25bebb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="1c398-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="1c398-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="1c398-103">Задает смещение для обработчика catch, созданный компилятором, являющийся оболочкой для асинхронного метода на промежуточном Языке.</span><span class="sxs-lookup"><span data-stu-id="1c398-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="1c398-104">Смещение на промежуточном Языке созданный catch используется отладчиком для обработки catch, как если бы не написанный пользователем, несмотря на то, что она может возникать в метода кода пользователя.</span><span class="sxs-lookup"><span data-stu-id="1c398-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="1c398-105">В частности, он используется в ответ на **CatchHandlerFound** события исключения.</span><span class="sxs-lookup"><span data-stu-id="1c398-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c398-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c398-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c398-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c398-107">Parameters</span></span>  
  
|<span data-ttu-id="1c398-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="1c398-108">Parameter</span></span>|<span data-ttu-id="1c398-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1c398-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="1c398-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1c398-110">Return Value</span></span>  
 <span data-ttu-id="1c398-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="1c398-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c398-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1c398-112">Requirements</span></span>  
 <span data-ttu-id="1c398-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1c398-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c398-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1c398-114">See Also</span></span>  
 [<span data-ttu-id="1c398-115">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="1c398-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
