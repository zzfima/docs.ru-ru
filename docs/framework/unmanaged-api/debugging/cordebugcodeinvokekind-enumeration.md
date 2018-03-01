---
title: "Перечисление CorDebugCodeInvokeKind"
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
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 10b45938cfe63fa98fdb06bc20c66cc0f25c41a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="ab809-102">Перечисление CorDebugCodeInvokeKind</span><span class="sxs-lookup"><span data-stu-id="ab809-102">CorDebugCodeInvokeKind Enumeration</span></span>
<span data-ttu-id="ab809-103">Описывает, каким образом экспортируемая функция вызывает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="ab809-103">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab809-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab809-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="ab809-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ab809-105">Members</span></span>  
  
|<span data-ttu-id="ab809-106">Член</span><span class="sxs-lookup"><span data-stu-id="ab809-106">Member</span></span>|<span data-ttu-id="ab809-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ab809-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="ab809-108">Если любой управляемый код вызывается этим методом, он должен находиться после явно заданных событий или точек останова.</span><span class="sxs-lookup"><span data-stu-id="ab809-108">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="ab809-109">— или —</span><span class="sxs-lookup"><span data-stu-id="ab809-109">--or--</span></span><br /><br /> <span data-ttu-id="ab809-110">Мы можем просто пропустить некоторую часть управляемого кода, который вызывает этот метод, так как не существует никакого простого способа останова на нем.</span><span class="sxs-lookup"><span data-stu-id="ab809-110">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="ab809-111">— или —</span><span class="sxs-lookup"><span data-stu-id="ab809-111">--or--</span></span><br /><br /> <span data-ttu-id="ab809-112">Метод может никогда не вызвать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="ab809-112">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="ab809-113">Этот метод будет вызывать управляемый код с помощью инструкции return.</span><span class="sxs-lookup"><span data-stu-id="ab809-113">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="ab809-114">Режим пропуска должен начаться в следующем управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="ab809-114">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="ab809-115">Этот метод будет вызывать управляемый код с помощью вызова с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="ab809-115">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="ab809-116">Пошаговый режим и режим пропуска любых инструкций вызова должны поступать в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="ab809-116">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab809-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="ab809-117">Remarks</span></span>  
 <span data-ttu-id="ab809-118">Это перечисление используется методом [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) информацию о пошаговом выполнении управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ab809-118">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab809-119">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ab809-119">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab809-120">Требования</span><span class="sxs-lookup"><span data-stu-id="ab809-120">Requirements</span></span>  
 <span data-ttu-id="ab809-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab809-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab809-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab809-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab809-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab809-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab809-124">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab809-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab809-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ab809-125">See Also</span></span>  
 [<span data-ttu-id="ab809-126">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="ab809-126">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="ab809-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="ab809-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
