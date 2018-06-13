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
ms.openlocfilehash: 2898f530fe3f9368778d0f854e8254f7b32d5293
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404941"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="707c2-102">Перечисление CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="707c2-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="707c2-103">Указывает тип обработки.</span><span class="sxs-lookup"><span data-stu-id="707c2-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="707c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="707c2-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="707c2-105">Участники</span><span class="sxs-lookup"><span data-stu-id="707c2-105">Members</span></span>  
  
|<span data-ttu-id="707c2-106">Член</span><span class="sxs-lookup"><span data-stu-id="707c2-106">Member</span></span>|<span data-ttu-id="707c2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="707c2-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="707c2-108">Этот дескриптор является строгим, запрещающая объект будет уничтожен во время сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="707c2-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="707c2-109">Дескриптор является ненадежным, которой не запрещает объект будет уничтожен во время сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="707c2-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="707c2-110">Дескриптор становится недействительным, когда объект собираются.</span><span class="sxs-lookup"><span data-stu-id="707c2-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="707c2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="707c2-111">Requirements</span></span>  
 <span data-ttu-id="707c2-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="707c2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="707c2-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="707c2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="707c2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="707c2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="707c2-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="707c2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="707c2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="707c2-116">See Also</span></span>  
 [<span data-ttu-id="707c2-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="707c2-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
