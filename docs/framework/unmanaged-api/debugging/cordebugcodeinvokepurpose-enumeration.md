---
title: "Перечисление CorDebugCodeInvokePurpose"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugInvokePurpose
api_location: mscordbi.dll
api_type: COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41938a11d7d92fd728772aa45bd8e97f137e5d69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="1d2e0-102">Перечисление CorDebugCodeInvokePurpose</span><span class="sxs-lookup"><span data-stu-id="1d2e0-102">CorDebugCodeInvokePurpose Enumeration</span></span>
<span data-ttu-id="1d2e0-103">Описывает, почему экспортируемая функция вызывает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="1d2e0-103">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d2e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d2e0-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="1d2e0-105">Члены</span><span class="sxs-lookup"><span data-stu-id="1d2e0-105">Members</span></span>  
  
|<span data-ttu-id="1d2e0-106">Член</span><span class="sxs-lookup"><span data-stu-id="1d2e0-106">Member</span></span>|<span data-ttu-id="1d2e0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1d2e0-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="1d2e0-108">Отсутствует или неизвестно.</span><span class="sxs-lookup"><span data-stu-id="1d2e0-108">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="1d2e0-109">Управляемый код будет выполнять любую управляемую точку входа, например, обратный p-invoke.</span><span class="sxs-lookup"><span data-stu-id="1d2e0-109">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="1d2e0-110">Любые дополнительные цели неизвестны среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="1d2e0-110">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="1d2e0-111">Управляемый код будет выполнять статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="1d2e0-111">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="1d2e0-112">Управляемый код будет выполнять реализацию некоторого метода интерфейса, который был вызван.</span><span class="sxs-lookup"><span data-stu-id="1d2e0-112">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d2e0-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d2e0-113">Remarks</span></span>  
 <span data-ttu-id="1d2e0-114">Это перечисление используется методом [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) информацию о пошаговом выполнении управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="1d2e0-114">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d2e0-115">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1d2e0-115">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d2e0-116">Требования</span><span class="sxs-lookup"><span data-stu-id="1d2e0-116">Requirements</span></span>  
 <span data-ttu-id="1d2e0-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d2e0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d2e0-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d2e0-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d2e0-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d2e0-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d2e0-120">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d2e0-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d2e0-121">См. также</span><span class="sxs-lookup"><span data-stu-id="1d2e0-121">See Also</span></span>  
 [<span data-ttu-id="1d2e0-122">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="1d2e0-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="1d2e0-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="1d2e0-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
