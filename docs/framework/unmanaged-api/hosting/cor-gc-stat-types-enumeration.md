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
ms.openlocfilehash: b0fbc462283ef1577de8100e60fd09caa53db539
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131916"
---
# <a name="cor_gc_stat_types-enumeration"></a><span data-ttu-id="0698f-102">Перечисление COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="0698f-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="0698f-103">Указывает статистику, записываемую для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0698f-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0698f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0698f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="0698f-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="0698f-105">Remarks</span></span>  
 <span data-ttu-id="0698f-106">Это перечисление указывает, какая статистика в структуре [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) должна быть задана методом [Иклргкманажер:: stats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0698f-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="0698f-107">Члены</span><span class="sxs-lookup"><span data-stu-id="0698f-107">Members</span></span>  
  
|<span data-ttu-id="0698f-108">Член</span><span class="sxs-lookup"><span data-stu-id="0698f-108">Member</span></span>|<span data-ttu-id="0698f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0698f-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="0698f-110">Записывает количество сборок мусора, выполненных для каждого поколения.</span><span class="sxs-lookup"><span data-stu-id="0698f-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="0698f-111">Записывает статистику использования памяти и размера сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0698f-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0698f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0698f-112">Requirements</span></span>  
 <span data-ttu-id="0698f-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0698f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0698f-114">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="0698f-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="0698f-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0698f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0698f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0698f-116">See also</span></span>

- [<span data-ttu-id="0698f-117">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="0698f-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="0698f-118">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="0698f-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
