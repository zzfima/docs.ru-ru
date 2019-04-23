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
ms.openlocfilehash: 9e228cfbdade420c4d5248ffd417c6131083ee74
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110421"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="e3937-102">Перечисление COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="e3937-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="e3937-103">Указывает статистические данные для записи для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e3937-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3937-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3937-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="e3937-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="e3937-105">Remarks</span></span>  
 <span data-ttu-id="e3937-106">Это перечисление определяет, какая именно статистика в [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) структуры должны задаваться в [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="e3937-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="e3937-107">Участники</span><span class="sxs-lookup"><span data-stu-id="e3937-107">Members</span></span>  
  
|<span data-ttu-id="e3937-108">Член</span><span class="sxs-lookup"><span data-stu-id="e3937-108">Member</span></span>|<span data-ttu-id="e3937-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e3937-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="e3937-110">Записи число сборов мусора, выполненных для каждого поколения.</span><span class="sxs-lookup"><span data-stu-id="e3937-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="e3937-111">Записи об использовании и сборка мусора коллекции размер статистика памяти.</span><span class="sxs-lookup"><span data-stu-id="e3937-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3937-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e3937-112">Requirements</span></span>  
 <span data-ttu-id="e3937-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3937-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3937-114">**Заголовок.** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="e3937-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e3937-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3937-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3937-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e3937-116">See also</span></span>

- [<span data-ttu-id="e3937-117">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="e3937-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="e3937-118">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="e3937-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
