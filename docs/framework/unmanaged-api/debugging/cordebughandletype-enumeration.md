---
title: Перечисление CorDebugHandleType
ms.date: 03/30/2017
api_name:
- CorDebugHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugHandleType
helpviewer_keywords:
- CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 513fc93bdac71e2a3ba59ebb53fdde44f1659af5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220465"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="c5fb7-102">Перечисление CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="c5fb7-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="c5fb7-103">Указывает тип обработки.</span><span class="sxs-lookup"><span data-stu-id="c5fb7-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5fb7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5fb7-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="c5fb7-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c5fb7-105">Members</span></span>  
  
|<span data-ttu-id="c5fb7-106">Член</span><span class="sxs-lookup"><span data-stu-id="c5fb7-106">Member</span></span>|<span data-ttu-id="c5fb7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c5fb7-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="c5fb7-108">Этот дескриптор является строгим, запрещающая объект освобождается при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="c5fb7-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="c5fb7-109">Дескриптор является ненадежным, который запрещает объект освобождается при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="c5fb7-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="c5fb7-110">Дескриптор становится недействительным, если этот объект собран.</span><span class="sxs-lookup"><span data-stu-id="c5fb7-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5fb7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c5fb7-111">Requirements</span></span>  
 <span data-ttu-id="c5fb7-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5fb7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5fb7-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5fb7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5fb7-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5fb7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5fb7-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5fb7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5fb7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c5fb7-116">See also</span></span>

- [<span data-ttu-id="c5fb7-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="c5fb7-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
