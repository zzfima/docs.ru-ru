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
ms.openlocfilehash: 02ff60852a85d003deb68cae96a184ac8d61c65f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089416"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="dbfab-102">Перечисление COR_PUB_ENUMPROCESS</span><span class="sxs-lookup"><span data-stu-id="dbfab-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="dbfab-103">Идентифицирует тип процесса для перечисления.</span><span class="sxs-lookup"><span data-stu-id="dbfab-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbfab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dbfab-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="dbfab-105">Участники</span><span class="sxs-lookup"><span data-stu-id="dbfab-105">Members</span></span>  
  
|<span data-ttu-id="dbfab-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="dbfab-106">Member name</span></span>|<span data-ttu-id="dbfab-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dbfab-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="dbfab-108">Управляемый процесс.</span><span class="sxs-lookup"><span data-stu-id="dbfab-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbfab-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="dbfab-109">Remarks</span></span>  
 <span data-ttu-id="dbfab-110">Текущая версия неуправляемого API отладки перечисляет только управляемые процессы.</span><span class="sxs-lookup"><span data-stu-id="dbfab-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbfab-111">Требования</span><span class="sxs-lookup"><span data-stu-id="dbfab-111">Requirements</span></span>  
 <span data-ttu-id="dbfab-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbfab-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbfab-113">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="dbfab-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="dbfab-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbfab-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="dbfab-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dbfab-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dbfab-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dbfab-116">See also</span></span>

- [<span data-ttu-id="dbfab-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="dbfab-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
