---
title: Перечисление COR_GC_STAT_TYPES
ms.date: 03/30/2017
api_name:
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fdfe33c5b488d8f464001a86233124d4e7df0ed
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779065"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="84957-102">Перечисление COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="84957-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="84957-103">Указывает статистические данные для записи для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="84957-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84957-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84957-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="84957-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="84957-105">Remarks</span></span>  
 <span data-ttu-id="84957-106">Это перечисление определяет, какая именно статистика в [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) структуры должны задаваться в [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="84957-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="84957-107">Участники</span><span class="sxs-lookup"><span data-stu-id="84957-107">Members</span></span>  
  
|<span data-ttu-id="84957-108">Член</span><span class="sxs-lookup"><span data-stu-id="84957-108">Member</span></span>|<span data-ttu-id="84957-109">Описание</span><span class="sxs-lookup"><span data-stu-id="84957-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="84957-110">Записи число сборов мусора, выполненных для каждого поколения.</span><span class="sxs-lookup"><span data-stu-id="84957-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="84957-111">Записи об использовании и сборка мусора коллекции размер статистика памяти.</span><span class="sxs-lookup"><span data-stu-id="84957-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84957-112">Требования</span><span class="sxs-lookup"><span data-stu-id="84957-112">Requirements</span></span>  
 <span data-ttu-id="84957-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84957-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84957-114">**Заголовок.** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="84957-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="84957-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84957-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84957-116">См. также</span><span class="sxs-lookup"><span data-stu-id="84957-116">See also</span></span>

- [<span data-ttu-id="84957-117">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="84957-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="84957-118">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="84957-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
