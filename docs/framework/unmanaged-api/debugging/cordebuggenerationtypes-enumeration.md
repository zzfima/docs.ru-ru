---
title: Перечисление CorDebugGenerationTypes
ms.date: 03/30/2017
api_name:
- CorDebugGenerationTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGenerationTypes
helpviewer_keywords:
- CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type:
- apiref
ms.openlocfilehash: 6133b34a60fd06c1b75d69783760741b8de62071
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789344"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="b8565-102">Перечисление CorDebugGenerationTypes</span><span class="sxs-lookup"><span data-stu-id="b8565-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="b8565-103">Указывает на создание области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="b8565-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8565-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8565-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="b8565-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b8565-105">Members</span></span>  
  
|<span data-ttu-id="b8565-106">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="b8565-106">Member name</span></span>|<span data-ttu-id="b8565-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b8565-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="b8565-108">Поколение 0.</span><span class="sxs-lookup"><span data-stu-id="b8565-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="b8565-109">Поколение 1.</span><span class="sxs-lookup"><span data-stu-id="b8565-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="b8565-110">Поколение 2.</span><span class="sxs-lookup"><span data-stu-id="b8565-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="b8565-111">Куча больших объектов.</span><span class="sxs-lookup"><span data-stu-id="b8565-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8565-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="b8565-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8565-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b8565-113">Requirements</span></span>  
 <span data-ttu-id="b8565-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8565-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8565-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8565-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8565-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8565-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8565-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8565-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8565-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="b8565-118">See also</span></span>

- [<span data-ttu-id="b8565-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="b8565-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
