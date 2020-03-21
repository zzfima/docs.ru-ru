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
ms.openlocfilehash: 4c79d0e4e37f3f884651e49c8fff6db72fac4f50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179291"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="bf87e-102">Структура COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="bf87e-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="bf87e-103">Указывает изменения в относительном смещении функции.</span><span class="sxs-lookup"><span data-stu-id="bf87e-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf87e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf87e-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="bf87e-105">Члены</span><span class="sxs-lookup"><span data-stu-id="bf87e-105">Members</span></span>  
  
|<span data-ttu-id="bf87e-106">Участник</span><span class="sxs-lookup"><span data-stu-id="bf87e-106">Member</span></span>|<span data-ttu-id="bf87e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bf87e-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="bf87e-108">Старый промежуточный язык Microsoft (MSIL) смещен по отношению к началу функции.</span><span class="sxs-lookup"><span data-stu-id="bf87e-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="bf87e-109">Новый MSIL смещен иссяк по отношению к началу функции.</span><span class="sxs-lookup"><span data-stu-id="bf87e-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="bf87e-110">`true`если отображение известно, что является точным; в `false`противном случае, .</span><span class="sxs-lookup"><span data-stu-id="bf87e-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf87e-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf87e-111">Remarks</span></span>  
 <span data-ttu-id="bf87e-112">Формат карты заключается в следующем: отладчик `oldOffset` будет считать, что относится к СМЕЩЕНию MSIL в рамках оригинального, неизмененного кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="bf87e-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="bf87e-113">Параметр `newOffset` относится к соответствующему смещению MSIL в рамках нового инструментируемого кода.</span><span class="sxs-lookup"><span data-stu-id="bf87e-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="bf87e-114">Для правильной работы необходимо выполнить следующие требования:</span><span class="sxs-lookup"><span data-stu-id="bf87e-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="bf87e-115">Карта должна быть отсортирована в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="bf87e-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="bf87e-116">Инструментальный код MSIL не должен быть переупорядочен.</span><span class="sxs-lookup"><span data-stu-id="bf87e-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="bf87e-117">Исходный код MSIL не должен быть удален.</span><span class="sxs-lookup"><span data-stu-id="bf87e-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="bf87e-118">Карта должна включать записи для картирования всех точек последовательности из файла базы данных программы (PDB).</span><span class="sxs-lookup"><span data-stu-id="bf87e-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="bf87e-119">Карта не интерполирует недостающие записи.</span><span class="sxs-lookup"><span data-stu-id="bf87e-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="bf87e-120">В следующем примере показана карта и ее результаты.</span><span class="sxs-lookup"><span data-stu-id="bf87e-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="bf87e-121">Карта:</span><span class="sxs-lookup"><span data-stu-id="bf87e-121">Map:</span></span>  
  
- <span data-ttu-id="bf87e-122">0 старых смещений, 0 новых смещений</span><span class="sxs-lookup"><span data-stu-id="bf87e-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="bf87e-123">5 старых смещений, 10 новых смещений</span><span class="sxs-lookup"><span data-stu-id="bf87e-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="bf87e-124">9 старых смещений, 20 новых смещений</span><span class="sxs-lookup"><span data-stu-id="bf87e-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="bf87e-125">Результат:</span><span class="sxs-lookup"><span data-stu-id="bf87e-125">Results:</span></span>  
  
- <span data-ttu-id="bf87e-126">Старое смещение 0, 1, 2, 3 или 4 будет отображено на новое смещение 0.</span><span class="sxs-lookup"><span data-stu-id="bf87e-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="bf87e-127">Старый смещение 5, 6, 7 или 8 будет отображено на новые смещения 10.</span><span class="sxs-lookup"><span data-stu-id="bf87e-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="bf87e-128">Старое смещение 9 или выше будет отображено на новые смещения 20.</span><span class="sxs-lookup"><span data-stu-id="bf87e-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="bf87e-129">Новое смещение 0, 1, 2, 3, 4, 5, 6, 7, 8 или 9 будет отображено на старые смещения 0.</span><span class="sxs-lookup"><span data-stu-id="bf87e-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="bf87e-130">Новое смещение 10, 11, 12, 13, 14, 15, 16, 17, 18 или 19 будет отображено на старые смещения 5.</span><span class="sxs-lookup"><span data-stu-id="bf87e-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="bf87e-131">Новое смещение 20 или выше будет отображено на старый смещение 9.</span><span class="sxs-lookup"><span data-stu-id="bf87e-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf87e-132">Требования</span><span class="sxs-lookup"><span data-stu-id="bf87e-132">Requirements</span></span>  
 <span data-ttu-id="bf87e-133">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf87e-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf87e-134">**Заголовок:** CorDebug.idl, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="bf87e-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="bf87e-135">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf87e-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf87e-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf87e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf87e-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bf87e-137">See also</span></span>

- [<span data-ttu-id="bf87e-138">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="bf87e-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="bf87e-139">Отладки</span><span class="sxs-lookup"><span data-stu-id="bf87e-139">Debugging</span></span>](index.md)
