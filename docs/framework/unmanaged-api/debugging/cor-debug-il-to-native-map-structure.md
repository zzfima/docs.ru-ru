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
ms.openlocfilehash: babb1ace1385c241b782691f22bfb4fbb689e310
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274074"
---
# <a name="cor_debug_il_to_native_map-structure"></a><span data-ttu-id="c1afa-102">Структура COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="c1afa-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="c1afa-103">Содержит смещения, которые используются для сопоставления кода MSIL с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="c1afa-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1afa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1afa-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="c1afa-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c1afa-105">Members</span></span>  
  
|<span data-ttu-id="c1afa-106">Член</span><span class="sxs-lookup"><span data-stu-id="c1afa-106">Member</span></span>|<span data-ttu-id="c1afa-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c1afa-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="c1afa-108">Смещение кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="c1afa-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="c1afa-109">Смещение начала машинного кода.</span><span class="sxs-lookup"><span data-stu-id="c1afa-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="c1afa-110">Смещение конца машинного кода.</span><span class="sxs-lookup"><span data-stu-id="c1afa-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c1afa-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c1afa-111">Requirements</span></span>  
 <span data-ttu-id="c1afa-112">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1afa-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1afa-113">**Заголовок.** CorProf. idl, CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="c1afa-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="c1afa-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="c1afa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1afa-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1afa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1afa-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c1afa-116">See also</span></span>

- [<span data-ttu-id="c1afa-117">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="c1afa-117">GetILToNativeMapping Method</span></span>](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="c1afa-118">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="c1afa-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="c1afa-119">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="c1afa-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="c1afa-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="c1afa-120">Debugging</span></span>](index.md)
