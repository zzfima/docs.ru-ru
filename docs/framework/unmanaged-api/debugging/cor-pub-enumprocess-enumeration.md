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
ms.openlocfilehash: bfc576e1b4f0bf1666dcd585a24dbfa398e9abde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715859"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="c2e9c-102">Перечисление COR_PUB_ENUMPROCESS</span><span class="sxs-lookup"><span data-stu-id="c2e9c-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="c2e9c-103">Идентифицирует тип процесса для перечисления.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2e9c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2e9c-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="c2e9c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c2e9c-105">Members</span></span>  
  
|<span data-ttu-id="c2e9c-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="c2e9c-106">Member name</span></span>|<span data-ttu-id="c2e9c-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="c2e9c-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="c2e9c-108">Управляемый процесс.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2e9c-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2e9c-109">Remarks</span></span>  
 <span data-ttu-id="c2e9c-110">Текущая версия неуправляемого API отладки перечисляет только управляемые процессы.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2e9c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c2e9c-111">Requirements</span></span>  
 <span data-ttu-id="c2e9c-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2e9c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2e9c-113">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="c2e9c-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c2e9c-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2e9c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2e9c-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2e9c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2e9c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c2e9c-116">See also</span></span>
- [<span data-ttu-id="c2e9c-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="c2e9c-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
