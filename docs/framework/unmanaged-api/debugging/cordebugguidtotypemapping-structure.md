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
ms.openlocfilehash: 9dc7093edaf12e801a1e1adc52b0be823ff92b91
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079920"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="38214-102">Структура CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="38214-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="38214-103">Maps [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID для соответствующего объекта ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="38214-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38214-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38214-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="38214-105">Участники</span><span class="sxs-lookup"><span data-stu-id="38214-105">Members</span></span>  
  
|<span data-ttu-id="38214-106">Член</span><span class="sxs-lookup"><span data-stu-id="38214-106">Member</span></span>|<span data-ttu-id="38214-107">Описание</span><span class="sxs-lookup"><span data-stu-id="38214-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="38214-108">Идентификатор GUID для кэшированного [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типа.</span><span class="sxs-lookup"><span data-stu-id="38214-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="38214-109">Указатель на объект ICorDebugType, предоставляющий сведения о кэшируемый тип.</span><span class="sxs-lookup"><span data-stu-id="38214-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38214-110">Требования</span><span class="sxs-lookup"><span data-stu-id="38214-110">Requirements</span></span>  
 <span data-ttu-id="38214-111">**Платформы:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38214-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="38214-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38214-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38214-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38214-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38214-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38214-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38214-115">См. также</span><span class="sxs-lookup"><span data-stu-id="38214-115">See also</span></span>

- [<span data-ttu-id="38214-116">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="38214-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="38214-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="38214-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
