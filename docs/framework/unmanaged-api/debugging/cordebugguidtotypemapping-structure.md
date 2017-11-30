---
title: "Структура CorDebugGuidToTypeMapping"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: CorDebugGuidToTypeMapping
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugGuidToTypeMapping
helpviewer_keywords: CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e4c829f4a74c3d2e84a070dfbe5d35d89b1b7ae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="03eab-102">Структура CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="03eab-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="03eab-103">Maps [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID для соответствующего объекта ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="03eab-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03eab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03eab-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="03eab-105">Члены</span><span class="sxs-lookup"><span data-stu-id="03eab-105">Members</span></span>  
  
|<span data-ttu-id="03eab-106">Член</span><span class="sxs-lookup"><span data-stu-id="03eab-106">Member</span></span>|<span data-ttu-id="03eab-107">Описание</span><span class="sxs-lookup"><span data-stu-id="03eab-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="03eab-108">Идентификатор GUID кэшированные [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типа.</span><span class="sxs-lookup"><span data-stu-id="03eab-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="03eab-109">Указатель на объект ICorDebugType, предоставляющий сведения о кэшированных типе.</span><span class="sxs-lookup"><span data-stu-id="03eab-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03eab-110">Требования</span><span class="sxs-lookup"><span data-stu-id="03eab-110">Requirements</span></span>  
 <span data-ttu-id="03eab-111">**Платформы:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03eab-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="03eab-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03eab-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03eab-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03eab-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03eab-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03eab-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03eab-115">См. также</span><span class="sxs-lookup"><span data-stu-id="03eab-115">See Also</span></span>  
 [<span data-ttu-id="03eab-116">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="03eab-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="03eab-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="03eab-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
