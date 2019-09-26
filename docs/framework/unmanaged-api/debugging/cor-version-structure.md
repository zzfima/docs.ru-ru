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
ms.openlocfilehash: ffbe571ebc3d14c12e57b1f805d77e56e97d12e1
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274174"
---
# <a name="cor_version-structure"></a><span data-ttu-id="4d0fd-102">Структура COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="4d0fd-102">COR_VERSION Structure</span></span>
<span data-ttu-id="4d0fd-103">Содержит стандартный номер версии среды CLR, состоящий из четырех частей.</span><span class="sxs-lookup"><span data-stu-id="4d0fd-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d0fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d0fd-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="4d0fd-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4d0fd-105">Members</span></span>  
  
|<span data-ttu-id="4d0fd-106">Член</span><span class="sxs-lookup"><span data-stu-id="4d0fd-106">Member</span></span>|<span data-ttu-id="4d0fd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4d0fd-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="4d0fd-108">Основной номер версии.</span><span class="sxs-lookup"><span data-stu-id="4d0fd-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="4d0fd-109">Дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="4d0fd-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="4d0fd-110">Номер сборки.</span><span class="sxs-lookup"><span data-stu-id="4d0fd-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="4d0fd-111">Номер подсборки.</span><span class="sxs-lookup"><span data-stu-id="4d0fd-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d0fd-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d0fd-112">Remarks</span></span>  
 <span data-ttu-id="4d0fd-113">Если номер версии — 1.0.3705.288, то 1 — основной номер версии, 0 — дополнительный номер версии, 3705 — номер сборки, а 288 — номер подсборки.</span><span class="sxs-lookup"><span data-stu-id="4d0fd-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d0fd-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4d0fd-114">Requirements</span></span>  
 <span data-ttu-id="4d0fd-115">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d0fd-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d0fd-116">**Заголовок.** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="4d0fd-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="4d0fd-117">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="4d0fd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d0fd-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d0fd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d0fd-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4d0fd-119">See also</span></span>

- [<span data-ttu-id="4d0fd-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="4d0fd-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="4d0fd-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="4d0fd-121">Debugging</span></span>](index.md)
