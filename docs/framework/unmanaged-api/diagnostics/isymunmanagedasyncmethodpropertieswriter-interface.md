---
title: Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ec66e0064a8d6e8d4664dd8c727aa87621cfd8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427311"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="0f25e-102">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="0f25e-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="0f25e-103">Можно задать необязательный асинхронный метод сведения для каждого символа метод.</span><span class="sxs-lookup"><span data-stu-id="0f25e-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="0f25e-104">Всегда использовать с помощью открытого метода; то есть между вызовами [метод OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) и [метод CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="0f25e-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f25e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f25e-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="0f25e-106">Методы</span><span class="sxs-lookup"><span data-stu-id="0f25e-106">Methods</span></span>  
 <span data-ttu-id="0f25e-107">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="0f25e-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="0f25e-108">Метод</span><span class="sxs-lookup"><span data-stu-id="0f25e-108">Method</span></span>|<span data-ttu-id="0f25e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0f25e-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0f25e-110">Метод DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="0f25e-110">DefineAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="0f25e-111">Определите группу async await операций в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="0f25e-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="0f25e-112">Смещение каждого yield соответствует инструкции return await, идентификации потенциальных yield.</span><span class="sxs-lookup"><span data-stu-id="0f25e-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="0f25e-113">Каждый `breakpointMethod` / `breakpointOffset` пары определяет, где будет возобновлена асинхронную операцию; он может находиться в другой метод.</span><span class="sxs-lookup"><span data-stu-id="0f25e-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="0f25e-114">Метод DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="0f25e-114">DefineCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="0f25e-115">Задает смещение для обработчика catch, созданный компилятором, являющийся оболочкой для асинхронного метода на промежуточном Языке.</span><span class="sxs-lookup"><span data-stu-id="0f25e-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="0f25e-116">Смещение на промежуточном Языке созданный catch используется отладчиком для обработки catch, как если бы это был не написанный пользователем код, несмотря на то, что эта проблема может возникнуть в метода кода пользователя.</span><span class="sxs-lookup"><span data-stu-id="0f25e-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="0f25e-117">В частности, он используется в ответ на **CatchHandlerFound** события исключения.</span><span class="sxs-lookup"><span data-stu-id="0f25e-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="0f25e-118">Метод DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="0f25e-118">DefineKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="0f25e-119">Задает начальный метод, который инициирует асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="0f25e-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0f25e-120">Требования</span><span class="sxs-lookup"><span data-stu-id="0f25e-120">Requirements</span></span>  
 <span data-ttu-id="0f25e-121">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0f25e-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f25e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0f25e-122">See Also</span></span>  
 [<span data-ttu-id="0f25e-123">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="0f25e-123">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
