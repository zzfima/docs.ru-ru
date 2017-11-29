---
title: "Перечисление CorDebugDebugEventKind"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugDebugEventKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5aeb6085671e645e12713944d6456b9581a3886f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="d7a29-102">Перечисление CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="d7a29-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="d7a29-103">Указывает тип события, сведения о которых декодирует [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="d7a29-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7a29-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7a29-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="d7a29-105">Члены</span><span class="sxs-lookup"><span data-stu-id="d7a29-105">Members</span></span>  
  
|<span data-ttu-id="d7a29-106">Член</span><span class="sxs-lookup"><span data-stu-id="d7a29-106">Member</span></span>|<span data-ttu-id="d7a29-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d7a29-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="d7a29-108">Событие загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="d7a29-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="d7a29-109">Событие выгрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="d7a29-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="d7a29-110">Первичное исключение.</span><span class="sxs-lookup"><span data-stu-id="d7a29-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="d7a29-111">Первичное исключение пользователя.</span><span class="sxs-lookup"><span data-stu-id="d7a29-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="d7a29-112">Исключение, для которого существует обработчик `catch`.</span><span class="sxs-lookup"><span data-stu-id="d7a29-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="d7a29-113">Необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="d7a29-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7a29-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7a29-114">Remarks</span></span>  
 <span data-ttu-id="d7a29-115">Член `CorDebugDebugEventKind` перечисления, возвращенный при вызове [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="d7a29-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7a29-116">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d7a29-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7a29-117">Требования</span><span class="sxs-lookup"><span data-stu-id="d7a29-117">Requirements</span></span>  
 <span data-ttu-id="d7a29-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7a29-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7a29-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7a29-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7a29-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7a29-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7a29-121">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7a29-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a29-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d7a29-122">See Also</span></span>  
 [<span data-ttu-id="d7a29-123">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="d7a29-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
