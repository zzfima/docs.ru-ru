---
title: Перечисление CorDebugMappingResult
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ca3f5a6af6ea19ec81af3f6ac0a028440f80d56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="33096-102">Перечисление CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="33096-102">CorDebugMappingResult Enumeration</span></span>
<span data-ttu-id="33096-103">Предоставляет сведения о том, как было получено значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="33096-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33096-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33096-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="33096-105">Участники</span><span class="sxs-lookup"><span data-stu-id="33096-105">Members</span></span>  
  
|<span data-ttu-id="33096-106">Член</span><span class="sxs-lookup"><span data-stu-id="33096-106">Member</span></span>|<span data-ttu-id="33096-107">Описание</span><span class="sxs-lookup"><span data-stu-id="33096-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="33096-108">Машинный код находится в прологе, поэтому значение IP равно 0.</span><span class="sxs-lookup"><span data-stu-id="33096-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="33096-109">Машинный код находится в эпилоге, поэтому значение IP-адрес последней инструкции метода.</span><span class="sxs-lookup"><span data-stu-id="33096-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="33096-110">Нет сведений о сопоставлении для метода, поэтому значение IP равно 0.</span><span class="sxs-lookup"><span data-stu-id="33096-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="33096-111">Хотя сведения о сопоставлении для метода, текущий адрес не может быть сопоставлен код на промежуточном языке (MSIL).</span><span class="sxs-lookup"><span data-stu-id="33096-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="33096-112">IP-адрес равен 0.</span><span class="sxs-lookup"><span data-stu-id="33096-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="33096-113">Метод сопоставляет ровно код MSIL, либо была выполнена интерпретация кадра, поэтому значение IP-адреса является точным.</span><span class="sxs-lookup"><span data-stu-id="33096-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="33096-114">Метод успешно сопоставлен, но значение IP-адреса может быть приблизительным.</span><span class="sxs-lookup"><span data-stu-id="33096-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33096-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="33096-115">Remarks</span></span>  
 <span data-ttu-id="33096-116">Можно использовать [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) метод получения значения указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="33096-116">You can use the [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33096-117">Требования</span><span class="sxs-lookup"><span data-stu-id="33096-117">Requirements</span></span>  
 <span data-ttu-id="33096-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33096-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33096-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33096-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33096-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33096-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33096-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33096-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33096-122">См. также</span><span class="sxs-lookup"><span data-stu-id="33096-122">See Also</span></span>  
 [<span data-ttu-id="33096-123">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="33096-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
