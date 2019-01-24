---
title: Структура COR_ACTIVE_FUNCTION
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5adf43bd68db449e465ffe3517c9eb9d41a5c18a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502056"
---
# <a name="coractivefunction-structure"></a><span data-ttu-id="4c69a-102">Структура COR_ACTIVE_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="4c69a-102">COR_ACTIVE_FUNCTION Structure</span></span>
<span data-ttu-id="4c69a-103">Содержит сведения о функциях, которые в данный момент активны в кадрах потока.</span><span class="sxs-lookup"><span data-stu-id="4c69a-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="4c69a-104">Эта структура используется [ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4c69a-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c69a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c69a-105">Syntax</span></span>  
  
```  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="4c69a-106">Участники</span><span class="sxs-lookup"><span data-stu-id="4c69a-106">Members</span></span>  
  
|<span data-ttu-id="4c69a-107">Член</span><span class="sxs-lookup"><span data-stu-id="4c69a-107">Member</span></span>|<span data-ttu-id="4c69a-108">Описание</span><span class="sxs-lookup"><span data-stu-id="4c69a-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="4c69a-109">Указатель на владельца домена приложения `ilOffset` поля.</span><span class="sxs-lookup"><span data-stu-id="4c69a-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="4c69a-110">Указатель на владельца модуля `ilOffset` поля.</span><span class="sxs-lookup"><span data-stu-id="4c69a-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="4c69a-111">Указатель на владельца функции `ilOffset` поля.</span><span class="sxs-lookup"><span data-stu-id="4c69a-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="4c69a-112">Смещение промежуточного языка MSIL Microsoft кадра.</span><span class="sxs-lookup"><span data-stu-id="4c69a-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="4c69a-113">Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="4c69a-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4c69a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4c69a-114">Requirements</span></span>  
 <span data-ttu-id="4c69a-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c69a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c69a-116">**Заголовок.** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="4c69a-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="4c69a-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c69a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c69a-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c69a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c69a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4c69a-119">See also</span></span>
- [<span data-ttu-id="4c69a-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="4c69a-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="4c69a-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="4c69a-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
