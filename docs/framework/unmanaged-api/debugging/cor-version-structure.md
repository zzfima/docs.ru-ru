---
title: Структура COR_VERSION
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1f0a36d186c6d9788d43b075bf9d67c36ed1acb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740568"
---
# <a name="corversion-structure"></a><span data-ttu-id="1f678-102">Структура COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="1f678-102">COR_VERSION Structure</span></span>
<span data-ttu-id="1f678-103">Содержит стандартный номер версии среды CLR, состоящий из четырех частей.</span><span class="sxs-lookup"><span data-stu-id="1f678-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f678-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f678-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="1f678-105">Участники</span><span class="sxs-lookup"><span data-stu-id="1f678-105">Members</span></span>  
  
|<span data-ttu-id="1f678-106">Член</span><span class="sxs-lookup"><span data-stu-id="1f678-106">Member</span></span>|<span data-ttu-id="1f678-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1f678-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="1f678-108">Основной номер версии.</span><span class="sxs-lookup"><span data-stu-id="1f678-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="1f678-109">Дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="1f678-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="1f678-110">Номер сборки.</span><span class="sxs-lookup"><span data-stu-id="1f678-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="1f678-111">Номер вложенного построения.</span><span class="sxs-lookup"><span data-stu-id="1f678-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f678-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f678-112">Remarks</span></span>  
 <span data-ttu-id="1f678-113">Если номер версии равен 1.0.3705.288, 1 — номер основной версии, 0 — это дополнительный номер версии, 3705 — номер сборки и 288 — номер вложенного построения.</span><span class="sxs-lookup"><span data-stu-id="1f678-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f678-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1f678-114">Requirements</span></span>  
 <span data-ttu-id="1f678-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f678-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f678-116">**Заголовок.** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="1f678-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="1f678-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f678-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f678-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f678-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f678-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1f678-119">See also</span></span>

- [<span data-ttu-id="1f678-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="1f678-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="1f678-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="1f678-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
