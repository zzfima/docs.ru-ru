---
title: "Перечисление CorDebugMappingResult"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugMappingResult
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugMappingResult
helpviewer_keywords: CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 924cfec87b99cba9621af02d4e78e72094060ae8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="cad36-102">Перечисление CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="cad36-102">CorDebugMappingResult Enumeration</span></span>
<span data-ttu-id="cad36-103">Предоставляет сведения о том, как было получено значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="cad36-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cad36-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cad36-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="cad36-105">Участники</span><span class="sxs-lookup"><span data-stu-id="cad36-105">Members</span></span>  
  
|<span data-ttu-id="cad36-106">Член</span><span class="sxs-lookup"><span data-stu-id="cad36-106">Member</span></span>|<span data-ttu-id="cad36-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="cad36-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="cad36-108">Машинный код находится в прологе, поэтому значение IP равно 0.</span><span class="sxs-lookup"><span data-stu-id="cad36-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="cad36-109">Машинный код находится в эпилоге, поэтому значение IP-адрес последней инструкции метода.</span><span class="sxs-lookup"><span data-stu-id="cad36-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="cad36-110">Нет сведений о сопоставлении для метода, поэтому значение IP равно 0.</span><span class="sxs-lookup"><span data-stu-id="cad36-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="cad36-111">Хотя сведения о сопоставлении для метода, текущий адрес не может быть сопоставлен код на промежуточном языке (MSIL).</span><span class="sxs-lookup"><span data-stu-id="cad36-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="cad36-112">IP-адрес равен 0.</span><span class="sxs-lookup"><span data-stu-id="cad36-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="cad36-113">Метод сопоставляет ровно код MSIL, либо была выполнена интерпретация кадра, поэтому значение IP-адреса является точным.</span><span class="sxs-lookup"><span data-stu-id="cad36-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="cad36-114">Метод успешно сопоставлен, но значение IP-адреса может быть приблизительным.</span><span class="sxs-lookup"><span data-stu-id="cad36-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cad36-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="cad36-115">Remarks</span></span>  
 <span data-ttu-id="cad36-116">Можно использовать [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) метод получения значения указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="cad36-116">You can use the [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cad36-117">Требования</span><span class="sxs-lookup"><span data-stu-id="cad36-117">Requirements</span></span>  
 <span data-ttu-id="cad36-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cad36-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cad36-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cad36-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cad36-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cad36-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cad36-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cad36-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cad36-122">См. также</span><span class="sxs-lookup"><span data-stu-id="cad36-122">See Also</span></span>  
 [<span data-ttu-id="cad36-123">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="cad36-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
