---
title: Структура COR_IL_MAP
ms.date: 03/30/2017
api_name:
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9676730a4f11ed77996b7a4aab4e538aba9b53c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="corilmap-structure"></a><span data-ttu-id="e85ab-102">Структура COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="e85ab-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="e85ab-103">Указывает изменения в относительном смещении функции.</span><span class="sxs-lookup"><span data-stu-id="e85ab-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e85ab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e85ab-104">Syntax</span></span>  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="e85ab-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e85ab-105">Members</span></span>  
  
|<span data-ttu-id="e85ab-106">Член</span><span class="sxs-lookup"><span data-stu-id="e85ab-106">Member</span></span>|<span data-ttu-id="e85ab-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e85ab-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="e85ab-108">Старый промежуточный язык Майкрософт (MSIL) смещение относительно начала функции.</span><span class="sxs-lookup"><span data-stu-id="e85ab-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="e85ab-109">Новое смещение MSIL относительно начала функции.</span><span class="sxs-lookup"><span data-stu-id="e85ab-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="e85ab-110">`true` Если сопоставление является точным; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="e85ab-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e85ab-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="e85ab-111">Remarks</span></span>  
 <span data-ttu-id="e85ab-112">Карты имеет следующий формат: отладчик предполагается, что `oldOffset` ссылается на смещение MSIL в пределах исходного, неизмененного MSIL-код.</span><span class="sxs-lookup"><span data-stu-id="e85ab-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="e85ab-113">`newOffset` Параметр ссылается на соответствующее смещение MSIL в новом инструментированном коде.</span><span class="sxs-lookup"><span data-stu-id="e85ab-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="e85ab-114">Для начала работы должным образом, должны выполняться следующие требования:</span><span class="sxs-lookup"><span data-stu-id="e85ab-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
-   <span data-ttu-id="e85ab-115">Карты должны быть отсортированы в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="e85ab-115">The map should be sorted in ascending order.</span></span>  
  
-   <span data-ttu-id="e85ab-116">Не требуется изменить порядок инструментированный код MSIL.</span><span class="sxs-lookup"><span data-stu-id="e85ab-116">Instrumented MSIL code should not be reordered.</span></span>  
  
-   <span data-ttu-id="e85ab-117">Не следует удалять исходный код MSIL.</span><span class="sxs-lookup"><span data-stu-id="e85ab-117">Original MSIL code should not be removed.</span></span>  
  
-   <span data-ttu-id="e85ab-118">При сопоставлении должны учитываться записи для сопоставления всех точек следования из файла базы данных (PDB) программы.</span><span class="sxs-lookup"><span data-stu-id="e85ab-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="e85ab-119">Карты не выполнять интерполяцию, отсутствующие записи.</span><span class="sxs-lookup"><span data-stu-id="e85ab-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="e85ab-120">В следующем примере показано сопоставление и его результаты.</span><span class="sxs-lookup"><span data-stu-id="e85ab-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="e85ab-121">Карта:</span><span class="sxs-lookup"><span data-stu-id="e85ab-121">Map:</span></span>  
  
-   <span data-ttu-id="e85ab-122">0 старое смещение, 0 новое смещение</span><span class="sxs-lookup"><span data-stu-id="e85ab-122">0 old offset, 0 new offset</span></span>  
  
-   <span data-ttu-id="e85ab-123">5 старое смещение, 10 новое смещение</span><span class="sxs-lookup"><span data-stu-id="e85ab-123">5 old offset, 10 new offset</span></span>  
  
-   <span data-ttu-id="e85ab-124">9 старое смещение, 20 новое смещение</span><span class="sxs-lookup"><span data-stu-id="e85ab-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="e85ab-125">Результаты:</span><span class="sxs-lookup"><span data-stu-id="e85ab-125">Results:</span></span>  
  
-   <span data-ttu-id="e85ab-126">Старое смещение 0, 1, 2, 3 или 4 будет сопоставлено новому смещению 0.</span><span class="sxs-lookup"><span data-stu-id="e85ab-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
-   <span data-ttu-id="e85ab-127">Старое смещение 5, 6, 7 или 8 будет сопоставлено новому смещению 10.</span><span class="sxs-lookup"><span data-stu-id="e85ab-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
-   <span data-ttu-id="e85ab-128">Старое смещение 9 или более поздней версии будут сопоставлены новому смещению 20.</span><span class="sxs-lookup"><span data-stu-id="e85ab-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
-   <span data-ttu-id="e85ab-129">Новое смещение 0, 1, 2, 3, 4, 5, 6, 7, 8 или 9 будет сопоставлено старому смещению 0.</span><span class="sxs-lookup"><span data-stu-id="e85ab-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
-   <span data-ttu-id="e85ab-130">Новый смещение 10, 11, 12, 13, 14, 15, 16, 17, 18 или 19 будет сопоставлено старому смещению 5.</span><span class="sxs-lookup"><span data-stu-id="e85ab-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
-   <span data-ttu-id="e85ab-131">Новое смещение 20 или выше будет сопоставлено старому смещению 9.</span><span class="sxs-lookup"><span data-stu-id="e85ab-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e85ab-132">Требования</span><span class="sxs-lookup"><span data-stu-id="e85ab-132">Requirements</span></span>  
 <span data-ttu-id="e85ab-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e85ab-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e85ab-134">**Заголовок:** CorDebug.idl, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="e85ab-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="e85ab-135">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e85ab-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e85ab-136">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e85ab-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e85ab-137">См. также</span><span class="sxs-lookup"><span data-stu-id="e85ab-137">See Also</span></span>  
 [<span data-ttu-id="e85ab-138">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="e85ab-138">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="e85ab-139">Отладка</span><span class="sxs-lookup"><span data-stu-id="e85ab-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
