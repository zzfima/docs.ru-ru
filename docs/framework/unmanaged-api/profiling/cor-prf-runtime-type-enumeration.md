---
title: "Перечисление COR_PRF_RUNTIME_TYPE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_RUNTIME_TYPE Enumeration
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_RUNTIME_TYPE
helpviewer_keywords: COR_PRF_RUNTIME_TYPE enumeration [.NET Framework profiling]
ms.assetid: 35449514-333f-4918-9c60-7aa198d655d2
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 154773e76046656e4286f4ba12717b6b45e9b069
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="9fff4-102">Перечисление COR_PRF_RUNTIME_TYPE</span><span class="sxs-lookup"><span data-stu-id="9fff4-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="9fff4-103">Содержит значения, указывающие версию среды common language runtime (CLR): рабочего стола и CoreCLR, который используется в Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9fff4-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fff4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fff4-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="9fff4-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9fff4-105">Members</span></span>  
  
|<span data-ttu-id="9fff4-106">Член</span><span class="sxs-lookup"><span data-stu-id="9fff4-106">Member</span></span>|<span data-ttu-id="9fff4-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="9fff4-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="9fff4-108">Версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9fff4-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="9fff4-109">Версия core CLR, используемых в Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9fff4-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fff4-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9fff4-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fff4-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9fff4-111">Requirements</span></span>  
 <span data-ttu-id="9fff4-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fff4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fff4-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9fff4-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9fff4-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fff4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fff4-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fff4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fff4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9fff4-116">See Also</span></span>  
 [<span data-ttu-id="9fff4-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="9fff4-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
