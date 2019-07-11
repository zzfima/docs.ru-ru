---
title: Перечисление COR_GC_THREAD_STATS_TYPES
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS_TYPES
helpviewer_keywords:
- COR_GC_THREAD_STATS_TYPES enumeration [.NET Framework hosting]
ms.assetid: aa227704-0ab1-4b08-aee2-1f439762162e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a984e8645bec0f58d8a31965b762e0a3a190ba59
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768017"
---
# <a name="corgcthreadstatstypes-enumeration"></a><span data-ttu-id="59158-102">Перечисление COR_GC_THREAD_STATS_TYPES</span><span class="sxs-lookup"><span data-stu-id="59158-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="59158-103">Указывает, статистика сборки мусора для потока.</span><span class="sxs-lookup"><span data-stu-id="59158-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59158-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59158-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="59158-105">Участники</span><span class="sxs-lookup"><span data-stu-id="59158-105">Members</span></span>  
  
|<span data-ttu-id="59158-106">Член</span><span class="sxs-lookup"><span data-stu-id="59158-106">Member</span></span>|<span data-ttu-id="59158-107">Описание</span><span class="sxs-lookup"><span data-stu-id="59158-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="59158-108">Поток имеет байт, которые были переданы в последней сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="59158-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59158-109">Требования</span><span class="sxs-lookup"><span data-stu-id="59158-109">Requirements</span></span>  
 <span data-ttu-id="59158-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59158-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59158-111">**Заголовок.** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="59158-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="59158-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59158-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59158-113">См. также</span><span class="sxs-lookup"><span data-stu-id="59158-113">See also</span></span>

- [<span data-ttu-id="59158-114">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="59158-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
