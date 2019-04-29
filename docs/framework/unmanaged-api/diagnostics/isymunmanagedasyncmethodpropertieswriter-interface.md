---
title: Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82fcddd7a3f89a92cc79285930b30342333fbec2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940105"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="b4dd7-102">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="b4dd7-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="b4dd7-103">Можно задать сведения о методе необязательно async для каждого символа метод.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="b4dd7-104">Всегда используйте с помощью открытого метода; то есть между вызовами [метод OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) и [метод CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="b4dd7-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4dd7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4dd7-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="b4dd7-106">Методы</span><span class="sxs-lookup"><span data-stu-id="b4dd7-106">Methods</span></span>  
 <span data-ttu-id="b4dd7-107">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="b4dd7-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="b4dd7-108">Метод</span><span class="sxs-lookup"><span data-stu-id="b4dd7-108">Method</span></span>|<span data-ttu-id="b4dd7-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b4dd7-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b4dd7-110">Метод DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="b4dd7-110">DefineAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="b4dd7-111">Определить группу async await операций в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="b4dd7-112">Смещение каждого yield соответствует инструкции return оператором await, определение потенциальных yield.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="b4dd7-113">Каждый `breakpointMethod` / `breakpointOffset` пары определяет, где будет возобновлена асинхронную операцию; он может находиться в другой метод.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="b4dd7-114">Метод DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="b4dd7-114">DefineCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="b4dd7-115">Задает смещение для обработчика catch, созданный компилятором, который создает оболочку для асинхронного метода на промежуточном Языке.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="b4dd7-116">Смещение на промежуточном Языке создаваемый catch используется отладчиком для обработки catch, как если бы это был не написанный пользователем код, несмотря на то, что эта проблема может возникнуть в коде пользовательского метода.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="b4dd7-117">В частности, он используется в ответ на **CatchHandlerFound** события исключения.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="b4dd7-118">Метод DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="b4dd7-118">DefineKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="b4dd7-119">Задает начальный метод, который инициирует асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="b4dd7-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4dd7-120">Требования</span><span class="sxs-lookup"><span data-stu-id="b4dd7-120">Requirements</span></span>  
 <span data-ttu-id="b4dd7-121">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b4dd7-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4dd7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b4dd7-122">See also</span></span>

- [<span data-ttu-id="b4dd7-123">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="b4dd7-123">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
