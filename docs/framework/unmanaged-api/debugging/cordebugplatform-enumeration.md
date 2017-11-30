---
title: "Перечисление CorDebugPlatform"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugPlatformEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugPlatformEnum
helpviewer_keywords: CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 52842d40895a658ec9dbb1263f18c48ec999a0ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="8c34e-102">Перечисление CorDebugPlatform</span><span class="sxs-lookup"><span data-stu-id="8c34e-102">CorDebugPlatform Enumeration</span></span>
<span data-ttu-id="8c34e-103">Предоставляет значения целевой платформы, которые используются в [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8c34e-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c34e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c34e-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="8c34e-105">Члены</span><span class="sxs-lookup"><span data-stu-id="8c34e-105">Members</span></span>  
  
|<span data-ttu-id="8c34e-106">Член</span><span class="sxs-lookup"><span data-stu-id="8c34e-106">Member</span></span>|<span data-ttu-id="8c34e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8c34e-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8c34e-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="8c34e-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="8c34e-109">Целевая платформа — ОС Windows, работающая на процессоре Intel x86.</span><span class="sxs-lookup"><span data-stu-id="8c34e-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="8c34e-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="8c34e-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="8c34e-111">Целевая платформа — 64-разрядная версия ОС Windows, работающая на процессоре AMD64 или Intel EM64T.</span><span class="sxs-lookup"><span data-stu-id="8c34e-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="8c34e-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="8c34e-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="8c34e-113">Целевая платформа — 32-разрядная версия ОС Windows, работающая на процессоре IA-64.</span><span class="sxs-lookup"><span data-stu-id="8c34e-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="8c34e-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="8c34e-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="8c34e-115">Целевая платформа — ОС Macintosh, работающая на процессоре PowerPC.</span><span class="sxs-lookup"><span data-stu-id="8c34e-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="8c34e-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="8c34e-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="8c34e-117">Целевая платформа — ОС Macintosh, работающая на процессоре Intel x86.</span><span class="sxs-lookup"><span data-stu-id="8c34e-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="8c34e-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="8c34e-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="8c34e-119">Целевая платформа — ОС Macintosh, работающая на процессоре Windows ARM.</span><span class="sxs-lookup"><span data-stu-id="8c34e-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="8c34e-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="8c34e-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="8c34e-121">Целевая платформа — ОС Macintosh, работающая на процессоре AMD64.</span><span class="sxs-lookup"><span data-stu-id="8c34e-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c34e-122">Требования</span><span class="sxs-lookup"><span data-stu-id="8c34e-122">Requirements</span></span>  
 <span data-ttu-id="8c34e-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c34e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c34e-124">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c34e-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c34e-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c34e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c34e-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c34e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="8c34e-127">Члены `CORDB_PLATFORM_WINDOWS_ARM` и `CORDB_PLATFORM_MAC_AMD64` доступны в платформе .NET Framework версии 4.5.2 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="8c34e-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c34e-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8c34e-128">See Also</span></span>  
 [<span data-ttu-id="8c34e-129">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="8c34e-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
