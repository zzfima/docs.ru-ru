---
title: Перечисление COR_PUB_ENUMPROCESS
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 412e2bb7da7b5b3396342df169d56d2724ddb466
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740549"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="6f22b-102">Перечисление COR_PUB_ENUMPROCESS</span><span class="sxs-lookup"><span data-stu-id="6f22b-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="6f22b-103">Идентифицирует тип процесса для перечисления.</span><span class="sxs-lookup"><span data-stu-id="6f22b-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f22b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f22b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="6f22b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="6f22b-105">Members</span></span>  
  
|<span data-ttu-id="6f22b-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="6f22b-106">Member name</span></span>|<span data-ttu-id="6f22b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6f22b-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="6f22b-108">Управляемый процесс.</span><span class="sxs-lookup"><span data-stu-id="6f22b-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f22b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="6f22b-109">Remarks</span></span>  
 <span data-ttu-id="6f22b-110">Текущая версия неуправляемого API отладки перечисляет только управляемые процессы.</span><span class="sxs-lookup"><span data-stu-id="6f22b-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f22b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6f22b-111">Requirements</span></span>  
 <span data-ttu-id="6f22b-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f22b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f22b-113">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="6f22b-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6f22b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f22b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f22b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f22b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f22b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6f22b-116">See also</span></span>

- [<span data-ttu-id="6f22b-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="6f22b-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
