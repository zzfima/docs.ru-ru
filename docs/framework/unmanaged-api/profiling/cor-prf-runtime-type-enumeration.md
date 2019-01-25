---
title: Перечисление COR_PRF_RUNTIME_TYPE
ms.date: 03/30/2017
api_name:
- COR_PRF_RUNTIME_TYPE Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_RUNTIME_TYPE
helpviewer_keywords:
- COR_PRF_RUNTIME_TYPE enumeration [.NET Framework profiling]
ms.assetid: 35449514-333f-4918-9c60-7aa198d655d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7c3a3581d2a9a1cb79f4ffe1d0a37269c18789a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652189"
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="8a4ee-102">Перечисление COR_PRF_RUNTIME_TYPE</span><span class="sxs-lookup"><span data-stu-id="8a4ee-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="8a4ee-103">Содержит значения, указывающие версию общеязыковой среды выполнения (CLR): рабочий стол или CoreCLR, который используется в Silverlight.</span><span class="sxs-lookup"><span data-stu-id="8a4ee-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a4ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a4ee-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="8a4ee-105">Участники</span><span class="sxs-lookup"><span data-stu-id="8a4ee-105">Members</span></span>  
  
|<span data-ttu-id="8a4ee-106">Член</span><span class="sxs-lookup"><span data-stu-id="8a4ee-106">Member</span></span>|<span data-ttu-id="8a4ee-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="8a4ee-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="8a4ee-108">Версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8a4ee-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="8a4ee-109">Основную версию среды CLR, используемый в Silverlight.</span><span class="sxs-lookup"><span data-stu-id="8a4ee-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a4ee-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="8a4ee-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a4ee-111">Требования</span><span class="sxs-lookup"><span data-stu-id="8a4ee-111">Requirements</span></span>  
 <span data-ttu-id="8a4ee-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a4ee-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a4ee-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a4ee-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a4ee-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a4ee-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a4ee-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a4ee-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a4ee-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8a4ee-116">See also</span></span>
- [<span data-ttu-id="8a4ee-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="8a4ee-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
