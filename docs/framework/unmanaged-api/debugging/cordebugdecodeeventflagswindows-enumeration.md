---
title: Перечисление CorDebugDecodeEventFlagsWindows
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
ms.openlocfilehash: da3a100bd552eaa3233642b006e0265adbcac1ca
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132216"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="dde80-102">Перечисление CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="dde80-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="dde80-103">Предоставляет дополнительную информацию о событиях отладки на платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="dde80-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dde80-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="dde80-105">Члены</span><span class="sxs-lookup"><span data-stu-id="dde80-105">Members</span></span>  
  
|<span data-ttu-id="dde80-106">Член</span><span class="sxs-lookup"><span data-stu-id="dde80-106">Member</span></span>|<span data-ttu-id="dde80-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dde80-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="dde80-108">Указывает, что событие отладки является первичным исключением.</span><span class="sxs-lookup"><span data-stu-id="dde80-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dde80-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="dde80-109">Remarks</span></span>  
 <span data-ttu-id="dde80-110">Метод [ICorDebugProcess6::D екодивент](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) включает параметр `dwFlags`, который предоставляет дополнительные сведения о событии отладки и значение которого зависит от целевой архитектуры.</span><span class="sxs-lookup"><span data-stu-id="dde80-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="dde80-111">Перечисление `CorDebugDecodeEventFlagsWindows` можно использовать с событиями отладки на платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="dde80-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dde80-112">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="dde80-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dde80-113">Требования</span><span class="sxs-lookup"><span data-stu-id="dde80-113">Requirements</span></span>  
 <span data-ttu-id="dde80-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dde80-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dde80-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dde80-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dde80-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dde80-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dde80-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dde80-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde80-118">См. также</span><span class="sxs-lookup"><span data-stu-id="dde80-118">See also</span></span>

- [<span data-ttu-id="dde80-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="dde80-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
