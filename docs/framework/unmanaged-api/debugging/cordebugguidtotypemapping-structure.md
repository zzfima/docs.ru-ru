---
title: Структура CorDebugGuidToTypeMapping
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38e1b19d6340f559e6f8b7e0f7bc042a10df16c3
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025998"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="0cfad-102">Структура CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="0cfad-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="0cfad-103">Сопоставляет GUID среды выполнения Windows для соответствующего объекта ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="0cfad-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cfad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0cfad-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="0cfad-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0cfad-105">Members</span></span>  
  
|<span data-ttu-id="0cfad-106">Член</span><span class="sxs-lookup"><span data-stu-id="0cfad-106">Member</span></span>|<span data-ttu-id="0cfad-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0cfad-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="0cfad-108">Идентификатор GUID кэшируемый тип среды выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="0cfad-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="0cfad-109">Указатель на объект ICorDebugType, предоставляющий сведения о кэшируемый тип.</span><span class="sxs-lookup"><span data-stu-id="0cfad-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0cfad-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0cfad-110">Requirements</span></span>  
 <span data-ttu-id="0cfad-111">**Платформы:** Среда выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="0cfad-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="0cfad-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cfad-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cfad-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cfad-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cfad-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cfad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cfad-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0cfad-115">See also</span></span>

- [<span data-ttu-id="0cfad-116">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="0cfad-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="0cfad-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="0cfad-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
