---
title: ICorProfilerCallback8::DynamicMethodJITCompilationМетод
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: e8b1a243b691d8d5eb364fd16821fd9156505c60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177050"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="69e25-102">ICorProfilerCallback8::DynamicMethodJITCompilationМетод</span><span class="sxs-lookup"><span data-stu-id="69e25-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="69e25-103">«Поддерживается в рамках .NET 4.7 и более поздних версиях»</span><span class="sxs-lookup"><span data-stu-id="69e25-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="69e25-104">Уведомляет профайлера всякий раз, когда начинается компиляция динамического метода JIT.</span><span class="sxs-lookup"><span data-stu-id="69e25-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e25-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69e25-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69e25-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="69e25-106">Parameters</span></span>  
<span data-ttu-id="69e25-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="69e25-107">[in] `functionId`</span></span>  
<span data-ttu-id="69e25-108">Идентификатор функции в памяти, для которой запускается компиляция JIT.</span><span class="sxs-lookup"><span data-stu-id="69e25-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="69e25-109">(в) `fIsSafeToBlock` указать, что блокировка может привести к тому, что время выполнения может привести к тому, что поток вызова вернется из этого обратного 
 `true` вызова; `false` указать, что блокировка не повлияет на работу времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="69e25-109">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="69e25-110">(в) `pILHeader` Указатель на первый байт IL заголовка метода.</span><span class="sxs-lookup"><span data-stu-id="69e25-110">[in] `pILHeader` A pointer to the first byte of the method's IL header.</span></span>

<span data-ttu-id="69e25-111">(в) `cbILHeader` Количество байтов в заголовке IL.</span><span class="sxs-lookup"><span data-stu-id="69e25-111">[in] `cbILHeader` The number of bytes in the IL header.</span></span>

## <a name="remarks"></a><span data-ttu-id="69e25-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="69e25-112">Remarks</span></span>  

<span data-ttu-id="69e25-113">Этот обратный вызов запускается всякий раз, когда динамический метод jIT-компилируется.</span><span class="sxs-lookup"><span data-stu-id="69e25-113">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="69e25-114">Это включает в себя различные заглушки IL и методы LCG.</span><span class="sxs-lookup"><span data-stu-id="69e25-114">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="69e25-115">Его цель заключается в предоставлении сценаристам-профилировщикам достаточно информации для идентификации компилированного метода для пользователей.</span><span class="sxs-lookup"><span data-stu-id="69e25-115">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="69e25-116">`functionId`значения не могут быть использованы для разрешения их токенов метаданных, поскольку динамические методы не имеют метаданных.</span><span class="sxs-lookup"><span data-stu-id="69e25-116">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="69e25-117">Указатель `pILHeader` действителен только во время обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="69e25-117">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="69e25-118">Требования</span><span class="sxs-lookup"><span data-stu-id="69e25-118">Requirements</span></span>  
 <span data-ttu-id="69e25-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69e25-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69e25-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69e25-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="69e25-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69e25-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69e25-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="69e25-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e25-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="69e25-123">See also</span></span>

- [<span data-ttu-id="69e25-124">Метод DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="69e25-124">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="69e25-125">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="69e25-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
