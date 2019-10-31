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
ms.openlocfilehash: 313f6649448653ad630d616c7dbf739653e352dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132840"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="107da-102">Структура CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="107da-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="107da-103">Сопоставляет идентификатор GUID среда выполнения Windows с соответствующим объектом ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="107da-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="107da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="107da-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="107da-105">Члены</span><span class="sxs-lookup"><span data-stu-id="107da-105">Members</span></span>  
  
|<span data-ttu-id="107da-106">Член</span><span class="sxs-lookup"><span data-stu-id="107da-106">Member</span></span>|<span data-ttu-id="107da-107">Описание</span><span class="sxs-lookup"><span data-stu-id="107da-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="107da-108">Идентификатор GUID кэшированного типа среда выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="107da-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="107da-109">Указатель на объект ICorDebugType, предоставляющий сведения о кэшированном типе.</span><span class="sxs-lookup"><span data-stu-id="107da-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="107da-110">Требования</span><span class="sxs-lookup"><span data-stu-id="107da-110">Requirements</span></span>  
 <span data-ttu-id="107da-111">**Платформы:** среда выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="107da-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="107da-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="107da-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="107da-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="107da-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="107da-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="107da-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="107da-115">См. также</span><span class="sxs-lookup"><span data-stu-id="107da-115">See also</span></span>

- [<span data-ttu-id="107da-116">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="107da-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="107da-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="107da-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
