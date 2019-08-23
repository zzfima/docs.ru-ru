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
ms.openlocfilehash: 4b5de58caeeac5ae85402e91a1402958e68336bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967593"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="80789-102">Перечисление CorDebugCodeInvokePurpose</span><span class="sxs-lookup"><span data-stu-id="80789-102">CorDebugCodeInvokePurpose Enumeration</span></span>
<span data-ttu-id="80789-103">Описывает, почему экспортируемая функция вызывает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="80789-103">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80789-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80789-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="80789-105">Участники</span><span class="sxs-lookup"><span data-stu-id="80789-105">Members</span></span>  
  
|<span data-ttu-id="80789-106">Член</span><span class="sxs-lookup"><span data-stu-id="80789-106">Member</span></span>|<span data-ttu-id="80789-107">Описание</span><span class="sxs-lookup"><span data-stu-id="80789-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="80789-108">Отсутствует или неизвестно.</span><span class="sxs-lookup"><span data-stu-id="80789-108">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="80789-109">Управляемый код будет выполнять любую управляемую точку входа, например, обратный p-invoke.</span><span class="sxs-lookup"><span data-stu-id="80789-109">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="80789-110">Любые дополнительные цели неизвестны среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="80789-110">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="80789-111">Управляемый код будет выполнять статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="80789-111">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="80789-112">Управляемый код будет выполнять реализацию некоторого метода интерфейса, который был вызван.</span><span class="sxs-lookup"><span data-stu-id="80789-112">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80789-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="80789-113">Remarks</span></span>  
 <span data-ttu-id="80789-114">Это перечисление используется методом [ICorDebugProcess6:: жетекспортстепинфо](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) для предоставления сведений о пошаговом выполнении управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="80789-114">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80789-115">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="80789-115">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80789-116">Требования</span><span class="sxs-lookup"><span data-stu-id="80789-116">Requirements</span></span>  
 <span data-ttu-id="80789-117">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80789-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80789-118">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="80789-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80789-119">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="80789-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80789-120">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80789-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80789-121">См. также</span><span class="sxs-lookup"><span data-stu-id="80789-121">See also</span></span>

- [<span data-ttu-id="80789-122">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="80789-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="80789-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="80789-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
