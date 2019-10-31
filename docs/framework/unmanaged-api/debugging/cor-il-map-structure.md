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
ms.openlocfilehash: c37f039d9636854c464e7981693c573bd60deab9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132343"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="ccee3-102">Структура COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="ccee3-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="ccee3-103">Указывает изменения в относительном смещении функции.</span><span class="sxs-lookup"><span data-stu-id="ccee3-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccee3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccee3-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="ccee3-105">Члены</span><span class="sxs-lookup"><span data-stu-id="ccee3-105">Members</span></span>  
  
|<span data-ttu-id="ccee3-106">Член</span><span class="sxs-lookup"><span data-stu-id="ccee3-106">Member</span></span>|<span data-ttu-id="ccee3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ccee3-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="ccee3-108">Старый сдвиг на языке MSIL относительно начала функции.</span><span class="sxs-lookup"><span data-stu-id="ccee3-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="ccee3-109">Новое смещение MSIL относительно начала функции.</span><span class="sxs-lookup"><span data-stu-id="ccee3-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="ccee3-110">`true`, если сопоставление известно как точное; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="ccee3-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccee3-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="ccee3-111">Remarks</span></span>  
 <span data-ttu-id="ccee3-112">Формат схемы выглядит следующим образом. отладчик предполагает, что `oldOffset` ссылается на смещение MSIL в исходном, неизмененном коде MSIL.</span><span class="sxs-lookup"><span data-stu-id="ccee3-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="ccee3-113">Параметр `newOffset` ссылается на соответствующее смещение MSIL в новом, инструментированном коде.</span><span class="sxs-lookup"><span data-stu-id="ccee3-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="ccee3-114">Чтобы пошаговая работа работала правильно, должны выполняться следующие требования:</span><span class="sxs-lookup"><span data-stu-id="ccee3-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="ccee3-115">Схема должна быть отсортирована в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="ccee3-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="ccee3-116">Не следует изменять порядок инструментированного кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="ccee3-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="ccee3-117">Исходный код MSIL не должен удаляться.</span><span class="sxs-lookup"><span data-stu-id="ccee3-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="ccee3-118">На карте должны содержаться записи, позволяющие сопоставлять все точки последовательности из файла базы данных программы (PDB).</span><span class="sxs-lookup"><span data-stu-id="ccee3-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="ccee3-119">На карте не выполняется интерполяция отсутствующих записей.</span><span class="sxs-lookup"><span data-stu-id="ccee3-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="ccee3-120">В следующем примере показана схема и ее результаты.</span><span class="sxs-lookup"><span data-stu-id="ccee3-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="ccee3-121">Таблица</span><span class="sxs-lookup"><span data-stu-id="ccee3-121">Map:</span></span>  
  
- <span data-ttu-id="ccee3-122">0 старое смещение, 0 новое смещение</span><span class="sxs-lookup"><span data-stu-id="ccee3-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="ccee3-123">5 старое смещение, 10 новых смещений</span><span class="sxs-lookup"><span data-stu-id="ccee3-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="ccee3-124">9 старое смещение, 20 новое смещение</span><span class="sxs-lookup"><span data-stu-id="ccee3-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="ccee3-125">Результаты</span><span class="sxs-lookup"><span data-stu-id="ccee3-125">Results:</span></span>  
  
- <span data-ttu-id="ccee3-126">Старое смещение 0, 1, 2, 3 или 4 будет сопоставлено с новым смещением, равным 0.</span><span class="sxs-lookup"><span data-stu-id="ccee3-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="ccee3-127">Старое смещение 5, 6, 7 или 8 будет сопоставлено с новым смещением 10.</span><span class="sxs-lookup"><span data-stu-id="ccee3-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="ccee3-128">Старое смещение 9 или выше будет сопоставлено с новым смещением 20.</span><span class="sxs-lookup"><span data-stu-id="ccee3-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="ccee3-129">Новое смещение 0, 1, 2, 3, 4, 5, 6, 7, 8 или 9 будет сопоставлено со старым смещением 0.</span><span class="sxs-lookup"><span data-stu-id="ccee3-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="ccee3-130">Новое смещение, равное 10, 11, 12, 13, 14, 15, 16, 17, 18 или 19, будет сопоставлено со старым смещением 5.</span><span class="sxs-lookup"><span data-stu-id="ccee3-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="ccee3-131">Новое смещение, равное 20 или выше, будет сопоставлено старому смещению 9.</span><span class="sxs-lookup"><span data-stu-id="ccee3-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccee3-132">Требования</span><span class="sxs-lookup"><span data-stu-id="ccee3-132">Requirements</span></span>  
 <span data-ttu-id="ccee3-133">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccee3-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccee3-134">**Заголовок:** CorDebug. idl, CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="ccee3-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="ccee3-135">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccee3-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccee3-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccee3-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccee3-137">См. также</span><span class="sxs-lookup"><span data-stu-id="ccee3-137">See also</span></span>

- [<span data-ttu-id="ccee3-138">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="ccee3-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="ccee3-139">Отладка</span><span class="sxs-lookup"><span data-stu-id="ccee3-139">Debugging</span></span>](index.md)
