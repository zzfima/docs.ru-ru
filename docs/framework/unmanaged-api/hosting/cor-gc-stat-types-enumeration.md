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
ms.openlocfilehash: eac378a48900d5820ad35587a6d269648ef99a77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428903"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="beb4d-102">Перечисление COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="beb4d-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="beb4d-103">Указывает статистику, записываемую для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="beb4d-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beb4d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="beb4d-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="beb4d-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="beb4d-105">Remarks</span></span>  
 <span data-ttu-id="beb4d-106">Это перечисление указывает, какая именно статистика в [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) структуры должны задаваться [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="beb4d-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="beb4d-107">Участники</span><span class="sxs-lookup"><span data-stu-id="beb4d-107">Members</span></span>  
  
|<span data-ttu-id="beb4d-108">Член</span><span class="sxs-lookup"><span data-stu-id="beb4d-108">Member</span></span>|<span data-ttu-id="beb4d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="beb4d-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="beb4d-110">Записи количество сборок мусора, выполненных для каждого поколения.</span><span class="sxs-lookup"><span data-stu-id="beb4d-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="beb4d-111">Записи об использовании и сборке мусора коллекции размер статистику памяти.</span><span class="sxs-lookup"><span data-stu-id="beb4d-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="beb4d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="beb4d-112">Requirements</span></span>  
 <span data-ttu-id="beb4d-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beb4d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beb4d-114">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="beb4d-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="beb4d-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beb4d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beb4d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="beb4d-116">See Also</span></span>  
 [<span data-ttu-id="beb4d-117">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="beb4d-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="beb4d-118">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="beb4d-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
