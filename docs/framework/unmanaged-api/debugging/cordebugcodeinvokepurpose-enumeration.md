---
title: Перечисление CorDebugCodeInvokePurpose
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4eeecc3b1c248f4f0bf4372801f6bc71a22f260
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662235"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="8a51f-102">Перечисление CorDebugCodeInvokePurpose</span><span class="sxs-lookup"><span data-stu-id="8a51f-102">CorDebugCodeInvokePurpose Enumeration</span></span>
<span data-ttu-id="8a51f-103">Описывает, почему экспортируемая функция вызывает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="8a51f-103">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a51f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a51f-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="8a51f-105">Участники</span><span class="sxs-lookup"><span data-stu-id="8a51f-105">Members</span></span>  
  
|<span data-ttu-id="8a51f-106">Член</span><span class="sxs-lookup"><span data-stu-id="8a51f-106">Member</span></span>|<span data-ttu-id="8a51f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8a51f-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="8a51f-108">Отсутствует или неизвестно.</span><span class="sxs-lookup"><span data-stu-id="8a51f-108">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="8a51f-109">Управляемый код будет выполнять любую управляемую точку входа, например, обратный p-invoke.</span><span class="sxs-lookup"><span data-stu-id="8a51f-109">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="8a51f-110">Любые дополнительные цели неизвестны среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="8a51f-110">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="8a51f-111">Управляемый код будет выполнять статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="8a51f-111">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="8a51f-112">Управляемый код будет выполнять реализацию некоторого метода интерфейса, который был вызван.</span><span class="sxs-lookup"><span data-stu-id="8a51f-112">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a51f-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="8a51f-113">Remarks</span></span>  
 <span data-ttu-id="8a51f-114">Это перечисление используется с [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) метод, чтобы предоставить сведения о пошаговом выполнении управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="8a51f-114">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a51f-115">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8a51f-115">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a51f-116">Требования</span><span class="sxs-lookup"><span data-stu-id="8a51f-116">Requirements</span></span>  
 <span data-ttu-id="8a51f-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a51f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a51f-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a51f-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a51f-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a51f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a51f-120">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a51f-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a51f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8a51f-121">See also</span></span>
- [<span data-ttu-id="8a51f-122">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="8a51f-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="8a51f-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="8a51f-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
