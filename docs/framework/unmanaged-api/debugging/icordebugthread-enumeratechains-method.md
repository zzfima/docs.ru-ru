---
title: "Метод ICorDebugThread::EnumerateChains"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e6a9637edb4a846b4d10dd6565533a9219ad558
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="ca827-102">Метод ICorDebugThread::EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="ca827-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="ca827-103">Получает указатель на интерфейс ICorDebugChainEnum перечислителя, который содержится в этом объекте ICorDebugThread всех цепочек стека.</span><span class="sxs-lookup"><span data-stu-id="ca827-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca827-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca827-104">Syntax</span></span>  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca827-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca827-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="ca827-106">[out] Указатель на адрес `ICorDebugChainEnum` связан объект, который позволяет использовать перечисления стека в этом потоке, начиная с цепочки active (то есть самой последней).</span><span class="sxs-lookup"><span data-stu-id="ca827-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca827-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ca827-107">Remarks</span></span>  
 <span data-ttu-id="ca827-108">Цепочка стека представляет физический стек вызова для потока.</span><span class="sxs-lookup"><span data-stu-id="ca827-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="ca827-109">Следующих обстоятельствах создайте границы цепи стека:</span><span class="sxs-lookup"><span data-stu-id="ca827-109">The following circumstances create a stack chain boundary:</span></span>  
  
-   <span data-ttu-id="ca827-110">Управляемый в неуправляемый или неуправляемый в управляемый переход.</span><span class="sxs-lookup"><span data-stu-id="ca827-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
-   <span data-ttu-id="ca827-111">Переключение контекста.</span><span class="sxs-lookup"><span data-stu-id="ca827-111">A context switch.</span></span>  
  
-   <span data-ttu-id="ca827-112">Значение типа отладчика перехват пользовательского потока.</span><span class="sxs-lookup"><span data-stu-id="ca827-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="ca827-113">В простом случае для потока, на котором выполняется только управляемый код в одном контексте однозначное соответствие будет использоваться между потоками и цепочек стека.</span><span class="sxs-lookup"><span data-stu-id="ca827-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="ca827-114">Отладчик может потребоваться переупорядочивание физических стеков вызова всех потоков в логические стеки вызова.</span><span class="sxs-lookup"><span data-stu-id="ca827-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="ca827-115">Организуется, сортировка по их связей "Вызывающий/вызываемый" цепочки всех потоков и перегруппирование.</span><span class="sxs-lookup"><span data-stu-id="ca827-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca827-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ca827-116">Requirements</span></span>  
 <span data-ttu-id="ca827-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca827-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca827-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca827-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca827-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca827-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca827-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca827-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
