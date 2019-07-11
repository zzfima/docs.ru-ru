---
title: Структура COR_DEBUG_IL_TO_NATIVE_MAP
ms.date: 03/30/2017
api_name:
- COR_DEBUG_IL_TO_NATIVE_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 238e59978bd084379fe6c0576107d674812bce8d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740780"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="5e18c-102">Структура COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="5e18c-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="5e18c-103">Содержит смещения, которые используются для сопоставления кода MSIL с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="5e18c-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e18c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e18c-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="5e18c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5e18c-105">Members</span></span>  
  
|<span data-ttu-id="5e18c-106">Член</span><span class="sxs-lookup"><span data-stu-id="5e18c-106">Member</span></span>|<span data-ttu-id="5e18c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5e18c-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="5e18c-108">Смещение MSIL-код.</span><span class="sxs-lookup"><span data-stu-id="5e18c-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="5e18c-109">Смещение начала машинного кода.</span><span class="sxs-lookup"><span data-stu-id="5e18c-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="5e18c-110">Смещение конца машинного кода.</span><span class="sxs-lookup"><span data-stu-id="5e18c-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e18c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5e18c-111">Requirements</span></span>  
 <span data-ttu-id="5e18c-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e18c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e18c-113">**Заголовок.** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="5e18c-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="5e18c-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e18c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e18c-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e18c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e18c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5e18c-116">See also</span></span>

- [<span data-ttu-id="5e18c-117">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="5e18c-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="5e18c-118">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="5e18c-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="5e18c-119">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="5e18c-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="5e18c-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="5e18c-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
