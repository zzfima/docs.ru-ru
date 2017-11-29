---
title: "Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dd84ea5ee00df3e59d4907cdf97bc36b7f06d993
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="dcd30-102">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="dcd30-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="dcd30-103">Можно задать необязательный асинхронный метод сведения для каждого символа метод.</span><span class="sxs-lookup"><span data-stu-id="dcd30-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="dcd30-104">Всегда использовать с помощью открытого метода; то есть между вызовами [метод OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) и [метод CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="dcd30-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcd30-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcd30-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="dcd30-106">Методы</span><span class="sxs-lookup"><span data-stu-id="dcd30-106">Methods</span></span>  
 <span data-ttu-id="dcd30-107">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="dcd30-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="dcd30-108">Метод</span><span class="sxs-lookup"><span data-stu-id="dcd30-108">Method</span></span>|<span data-ttu-id="dcd30-109">Описание</span><span class="sxs-lookup"><span data-stu-id="dcd30-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dcd30-110">Метод DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="dcd30-110">DefineAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="dcd30-111">Определите группу async await операций в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="dcd30-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="dcd30-112">Смещение каждого yield соответствует инструкции return await, идентификации потенциальных yield.</span><span class="sxs-lookup"><span data-stu-id="dcd30-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="dcd30-113">Каждый `breakpointMethod` / `breakpointOffset` пары определяет, где будет возобновлена асинхронную операцию; он может находиться в другой метод.</span><span class="sxs-lookup"><span data-stu-id="dcd30-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="dcd30-114">Метод DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="dcd30-114">DefineCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="dcd30-115">Задает смещение для обработчика catch, созданный компилятором, являющийся оболочкой для асинхронного метода на промежуточном Языке.</span><span class="sxs-lookup"><span data-stu-id="dcd30-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="dcd30-116">Смещение на промежуточном Языке созданный catch используется отладчиком для обработки catch, как если бы это был не написанный пользователем код, несмотря на то, что эта проблема может возникнуть в метода кода пользователя.</span><span class="sxs-lookup"><span data-stu-id="dcd30-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="dcd30-117">В частности, он используется в ответ на **CatchHandlerFound** события исключения.</span><span class="sxs-lookup"><span data-stu-id="dcd30-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="dcd30-118">Метод DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="dcd30-118">DefineKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="dcd30-119">Задает начальный метод, который инициирует асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="dcd30-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dcd30-120">Требования</span><span class="sxs-lookup"><span data-stu-id="dcd30-120">Requirements</span></span>  
 <span data-ttu-id="dcd30-121">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dcd30-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcd30-122">См. также</span><span class="sxs-lookup"><span data-stu-id="dcd30-122">See Also</span></span>  
 [<span data-ttu-id="dcd30-123">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="dcd30-123">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
