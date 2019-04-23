---
title: Перечисление CorDebugPlatform
ms.date: 03/30/2017
api_name:
- CorDebugPlatformEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugPlatformEnum
helpviewer_keywords:
- CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03b6f1b29157889d0e84e5dddc94d5e3ae27efce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180947"
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="d7722-102">Перечисление CorDebugPlatform</span><span class="sxs-lookup"><span data-stu-id="d7722-102">CorDebugPlatform Enumeration</span></span>
<span data-ttu-id="d7722-103">Предоставляет значения целевой платформы, используемые [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="d7722-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7722-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7722-104">Syntax</span></span>  
  
```  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a><span data-ttu-id="d7722-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d7722-105">Members</span></span>  
  
|<span data-ttu-id="d7722-106">Член</span><span class="sxs-lookup"><span data-stu-id="d7722-106">Member</span></span>|<span data-ttu-id="d7722-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d7722-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d7722-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="d7722-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="d7722-109">Целевая платформа — ОС Windows, работающая на процессоре Intel x86.</span><span class="sxs-lookup"><span data-stu-id="d7722-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="d7722-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="d7722-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="d7722-111">Целевая платформа — 64-разрядная версия ОС Windows, работающая на процессоре AMD64 или Intel EM64T.</span><span class="sxs-lookup"><span data-stu-id="d7722-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="d7722-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="d7722-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="d7722-113">Целевая платформа — 32-разрядная версия ОС Windows, работающая на процессоре IA-64.</span><span class="sxs-lookup"><span data-stu-id="d7722-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="d7722-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="d7722-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="d7722-115">Целевая платформа — ОС Macintosh, работающая на процессоре PowerPC.</span><span class="sxs-lookup"><span data-stu-id="d7722-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="d7722-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="d7722-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="d7722-117">Целевая платформа — ОС Macintosh, работающая на процессоре Intel x86.</span><span class="sxs-lookup"><span data-stu-id="d7722-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="d7722-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="d7722-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="d7722-119">Целевая платформа — ОС Macintosh, работающая на процессоре Windows ARM.</span><span class="sxs-lookup"><span data-stu-id="d7722-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="d7722-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="d7722-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="d7722-121">Целевая платформа — ОС Macintosh, работающая на процессоре AMD64.</span><span class="sxs-lookup"><span data-stu-id="d7722-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7722-122">Требования</span><span class="sxs-lookup"><span data-stu-id="d7722-122">Requirements</span></span>  
 <span data-ttu-id="d7722-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7722-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7722-124">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7722-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7722-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7722-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7722-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7722-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="d7722-127">Члены `CORDB_PLATFORM_WINDOWS_ARM` и `CORDB_PLATFORM_MAC_AMD64` доступны в платформе .NET Framework версии 4.5.2 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="d7722-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7722-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d7722-128">See also</span></span>

- [<span data-ttu-id="d7722-129">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="d7722-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
