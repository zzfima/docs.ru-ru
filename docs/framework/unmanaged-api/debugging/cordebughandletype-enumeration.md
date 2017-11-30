---
title: "Перечисление CorDebugHandleType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugHandleType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugHandleType
helpviewer_keywords: CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ef0b892d8dc277286114e8f9eda8d0f16833e1d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="d0be5-102">Перечисление CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="d0be5-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="d0be5-103">Указывает тип обработки.</span><span class="sxs-lookup"><span data-stu-id="d0be5-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0be5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0be5-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="d0be5-105">Члены</span><span class="sxs-lookup"><span data-stu-id="d0be5-105">Members</span></span>  
  
|<span data-ttu-id="d0be5-106">Член</span><span class="sxs-lookup"><span data-stu-id="d0be5-106">Member</span></span>|<span data-ttu-id="d0be5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d0be5-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="d0be5-108">Этот дескриптор является строгим, запрещающая объект будет уничтожен во время сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="d0be5-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="d0be5-109">Дескриптор является ненадежным, которой не запрещает объект будет уничтожен во время сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="d0be5-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="d0be5-110">Дескриптор становится недействительным, когда объект собираются.</span><span class="sxs-lookup"><span data-stu-id="d0be5-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d0be5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d0be5-111">Requirements</span></span>  
 <span data-ttu-id="d0be5-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0be5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0be5-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0be5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0be5-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0be5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0be5-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0be5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0be5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d0be5-116">See Also</span></span>  
 [<span data-ttu-id="d0be5-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="d0be5-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
