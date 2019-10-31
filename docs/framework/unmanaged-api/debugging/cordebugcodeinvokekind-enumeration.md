---
title: Перечисление CorDebugCodeInvokeKind
ms.date: 03/30/2017
api_name:
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
ms.openlocfilehash: cc839e9b2a28dc428ae7cc87c9d080c4b7612a9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098879"
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="bf292-102">Перечисление CorDebugCodeInvokeKind</span><span class="sxs-lookup"><span data-stu-id="bf292-102">CorDebugCodeInvokeKind Enumeration</span></span>
<span data-ttu-id="bf292-103">Описывает, каким образом экспортируемая функция вызывает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="bf292-103">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf292-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf292-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="bf292-105">Члены</span><span class="sxs-lookup"><span data-stu-id="bf292-105">Members</span></span>  
  
|<span data-ttu-id="bf292-106">Член</span><span class="sxs-lookup"><span data-stu-id="bf292-106">Member</span></span>|<span data-ttu-id="bf292-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bf292-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="bf292-108">Если любой управляемый код вызывается этим методом, он должен находиться после явно заданных событий или точек останова.</span><span class="sxs-lookup"><span data-stu-id="bf292-108">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="bf292-109">— или —</span><span class="sxs-lookup"><span data-stu-id="bf292-109">--or--</span></span><br /><br /> <span data-ttu-id="bf292-110">Мы можем просто пропустить некоторую часть управляемого кода, который вызывает этот метод, так как не существует никакого простого способа останова на нем.</span><span class="sxs-lookup"><span data-stu-id="bf292-110">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="bf292-111">— или —</span><span class="sxs-lookup"><span data-stu-id="bf292-111">--or--</span></span><br /><br /> <span data-ttu-id="bf292-112">Метод может никогда не вызвать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="bf292-112">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="bf292-113">Этот метод будет вызывать управляемый код с помощью инструкции return.</span><span class="sxs-lookup"><span data-stu-id="bf292-113">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="bf292-114">Режим пропуска должен начаться в следующем управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="bf292-114">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="bf292-115">Этот метод будет вызывать управляемый код с помощью вызова с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="bf292-115">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="bf292-116">Пошаговый режим и режим пропуска любых инструкций вызова должны поступать в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="bf292-116">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf292-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="bf292-117">Remarks</span></span>  
 <span data-ttu-id="bf292-118">Это перечисление используется методом [ICorDebugProcess6:: жетекспортстепинфо](icordebugprocess6-getexportstepinfo-method.md) для предоставления сведений о пошаговом выполнении управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="bf292-118">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf292-119">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bf292-119">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf292-120">Требования</span><span class="sxs-lookup"><span data-stu-id="bf292-120">Requirements</span></span>  
 <span data-ttu-id="bf292-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf292-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf292-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf292-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf292-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf292-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf292-124">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf292-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf292-125">См. также</span><span class="sxs-lookup"><span data-stu-id="bf292-125">See also</span></span>

- [<span data-ttu-id="bf292-126">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="bf292-126">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="bf292-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="bf292-127">Debugging</span></span>](index.md)
