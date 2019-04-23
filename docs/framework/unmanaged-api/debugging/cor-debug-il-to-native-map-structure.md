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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142055"
---
# <a name="cordebugiltonativemap-structure"></a><span data-ttu-id="20728-102">Структура COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="20728-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>
<span data-ttu-id="20728-103">Содержит смещения, которые используются для сопоставления кода MSIL с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="20728-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20728-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20728-104">Syntax</span></span>  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="20728-105">Участники</span><span class="sxs-lookup"><span data-stu-id="20728-105">Members</span></span>  
  
|<span data-ttu-id="20728-106">Член</span><span class="sxs-lookup"><span data-stu-id="20728-106">Member</span></span>|<span data-ttu-id="20728-107">Описание</span><span class="sxs-lookup"><span data-stu-id="20728-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="20728-108">Смещение MSIL-код.</span><span class="sxs-lookup"><span data-stu-id="20728-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="20728-109">Смещение начала машинного кода.</span><span class="sxs-lookup"><span data-stu-id="20728-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="20728-110">Смещение конца машинного кода.</span><span class="sxs-lookup"><span data-stu-id="20728-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="20728-111">Требования</span><span class="sxs-lookup"><span data-stu-id="20728-111">Requirements</span></span>  
 <span data-ttu-id="20728-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20728-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20728-113">**Заголовок.** CorProf.idl, CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="20728-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="20728-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20728-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20728-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20728-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20728-116">См. также</span><span class="sxs-lookup"><span data-stu-id="20728-116">See also</span></span>

- [<span data-ttu-id="20728-117">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="20728-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="20728-118">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="20728-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="20728-119">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="20728-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="20728-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="20728-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
