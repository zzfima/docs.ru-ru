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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079920"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="7ea55-102">Структура CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="7ea55-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="7ea55-103">Maps [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID для соответствующего объекта ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="7ea55-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ea55-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ea55-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="7ea55-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7ea55-105">Members</span></span>  
  
|<span data-ttu-id="7ea55-106">Член</span><span class="sxs-lookup"><span data-stu-id="7ea55-106">Member</span></span>|<span data-ttu-id="7ea55-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7ea55-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="7ea55-108">Идентификатор GUID для кэшированного [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типа.</span><span class="sxs-lookup"><span data-stu-id="7ea55-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="7ea55-109">Указатель на объект ICorDebugType, предоставляющий сведения о кэшируемый тип.</span><span class="sxs-lookup"><span data-stu-id="7ea55-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ea55-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7ea55-110">Requirements</span></span>  
 <span data-ttu-id="7ea55-111">**Платформы:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ea55-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="7ea55-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ea55-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ea55-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ea55-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7ea55-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7ea55-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7ea55-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7ea55-115">See also</span></span>

- [<span data-ttu-id="7ea55-116">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="7ea55-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="7ea55-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="7ea55-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
