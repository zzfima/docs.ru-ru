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
ms.openlocfilehash: 03ce77dd7407db8289abfefba13d71a9af053e10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609520"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="57651-102">Структура COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="57651-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="57651-103">Содержит смещения, которые используются для сопоставления кода MSIL с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="57651-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57651-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57651-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="57651-105">Участники</span><span class="sxs-lookup"><span data-stu-id="57651-105">Members</span></span>  
  
|<span data-ttu-id="57651-106">Член</span><span class="sxs-lookup"><span data-stu-id="57651-106">Member</span></span>|<span data-ttu-id="57651-107">Описание</span><span class="sxs-lookup"><span data-stu-id="57651-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="57651-108">Смещение MSIL-код.</span><span class="sxs-lookup"><span data-stu-id="57651-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="57651-109">Смещение начала машинного кода.</span><span class="sxs-lookup"><span data-stu-id="57651-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="57651-110">Смещение конца машинного кода.</span><span class="sxs-lookup"><span data-stu-id="57651-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57651-111">Требования</span><span class="sxs-lookup"><span data-stu-id="57651-111">Requirements</span></span>  
 <span data-ttu-id="57651-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57651-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57651-113">**Заголовок.** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="57651-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="57651-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57651-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57651-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57651-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57651-116">См. также</span><span class="sxs-lookup"><span data-stu-id="57651-116">See also</span></span>

- [<span data-ttu-id="57651-117">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="57651-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="57651-118">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="57651-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="57651-119">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="57651-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="57651-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="57651-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
