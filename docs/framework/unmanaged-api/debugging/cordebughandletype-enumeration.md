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
ms.openlocfilehash: f6f5cd47abd4c17021bc324898a096ff70a3db2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739994"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="4be1b-102">Перечисление CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="4be1b-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="4be1b-103">Указывает тип обработки.</span><span class="sxs-lookup"><span data-stu-id="4be1b-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4be1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4be1b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="4be1b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4be1b-105">Members</span></span>  
  
|<span data-ttu-id="4be1b-106">Член</span><span class="sxs-lookup"><span data-stu-id="4be1b-106">Member</span></span>|<span data-ttu-id="4be1b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4be1b-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="4be1b-108">Этот дескриптор является строгим, запрещающая объект освобождается при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="4be1b-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="4be1b-109">Дескриптор является ненадежным, который запрещает объект освобождается при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="4be1b-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="4be1b-110">Дескриптор становится недействительным, если этот объект собран.</span><span class="sxs-lookup"><span data-stu-id="4be1b-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4be1b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4be1b-111">Requirements</span></span>  
 <span data-ttu-id="4be1b-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4be1b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4be1b-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4be1b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4be1b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4be1b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4be1b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4be1b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4be1b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4be1b-116">See also</span></span>

- [<span data-ttu-id="4be1b-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="4be1b-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
