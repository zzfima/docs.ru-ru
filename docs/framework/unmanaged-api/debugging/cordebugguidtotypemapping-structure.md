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
ms.openlocfilehash: b855a53c9e4303138d7605bdf108d37bb345b917
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789329"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="74059-102">Структура CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="74059-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="74059-103">Сопоставляет идентификатор GUID среда выполнения Windows с соответствующим объектом ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="74059-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74059-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74059-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="74059-105">Участники</span><span class="sxs-lookup"><span data-stu-id="74059-105">Members</span></span>  
  
|<span data-ttu-id="74059-106">Член</span><span class="sxs-lookup"><span data-stu-id="74059-106">Member</span></span>|<span data-ttu-id="74059-107">Описание</span><span class="sxs-lookup"><span data-stu-id="74059-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="74059-108">Идентификатор GUID кэшированного типа среда выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="74059-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="74059-109">Указатель на объект ICorDebugType, предоставляющий сведения о кэшированном типе.</span><span class="sxs-lookup"><span data-stu-id="74059-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="74059-110">Требования</span><span class="sxs-lookup"><span data-stu-id="74059-110">Requirements</span></span>  
 <span data-ttu-id="74059-111">**Платформы:** среда выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="74059-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="74059-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74059-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74059-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74059-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74059-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74059-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74059-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="74059-115">See also</span></span>

- [<span data-ttu-id="74059-116">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="74059-116">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="74059-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="74059-117">Debugging</span></span>](index.md)
