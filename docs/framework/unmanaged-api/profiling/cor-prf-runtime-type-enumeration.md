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
ms.openlocfilehash: 26948261c571dbe963811e8e9631551685a63bdb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450370"
---
# <a name="cor_prf_runtime_type-enumeration"></a><span data-ttu-id="e34f9-102">Перечисление COR_PRF_RUNTIME_TYPE</span><span class="sxs-lookup"><span data-stu-id="e34f9-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="e34f9-103">Содержит значения, указывающие версию среды CLR: Desktop или CoreCLR, которая используется в Silverlight.</span><span class="sxs-lookup"><span data-stu-id="e34f9-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e34f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e34f9-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="e34f9-105">Члены</span><span class="sxs-lookup"><span data-stu-id="e34f9-105">Members</span></span>  
  
|<span data-ttu-id="e34f9-106">Член</span><span class="sxs-lookup"><span data-stu-id="e34f9-106">Member</span></span>|<span data-ttu-id="e34f9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e34f9-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="e34f9-108">Версия среды CLR для настольных систем.</span><span class="sxs-lookup"><span data-stu-id="e34f9-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="e34f9-109">Основная версия среды CLR, используемая в Silverlight.</span><span class="sxs-lookup"><span data-stu-id="e34f9-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e34f9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="e34f9-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e34f9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e34f9-111">Requirements</span></span>  
 <span data-ttu-id="e34f9-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e34f9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e34f9-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e34f9-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e34f9-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e34f9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e34f9-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e34f9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e34f9-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="e34f9-116">See also</span></span>

- [<span data-ttu-id="e34f9-117">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="e34f9-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
