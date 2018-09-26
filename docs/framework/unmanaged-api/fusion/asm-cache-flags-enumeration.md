---
title: Перечисление ASM_CACHE_FLAGS
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b712c6ae5978e83dab085f48dd1fd572757384a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47107900"
---
# <a name="asmcacheflags-enumeration"></a><span data-ttu-id="1e5f7-102">Перечисление ASM_CACHE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1e5f7-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="1e5f7-103">Указывает источник сборки, представленного [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="1e5f7-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e5f7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e5f7-104">Syntax</span></span>  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="1e5f7-105">Участники</span><span class="sxs-lookup"><span data-stu-id="1e5f7-105">Members</span></span>  
  
|<span data-ttu-id="1e5f7-106">Член</span><span class="sxs-lookup"><span data-stu-id="1e5f7-106">Member</span></span>|<span data-ttu-id="1e5f7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1e5f7-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="1e5f7-108">Перечисляет кэша предварительно скомпилированных сборок с помощью Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="1e5f7-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="1e5f7-109">Перечисляет глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="1e5f7-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="1e5f7-110">Перечисляет сборки, загруженные по запросу или которые были теневого копирования.</span><span class="sxs-lookup"><span data-stu-id="1e5f7-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="1e5f7-111">Указывает, что [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) функция должна возвращать путь в глобальном кэше сборок для общеязыковой среды выполнения (CLR) версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="1e5f7-111">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="1e5f7-112">Значение только в контексте вызова [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="1e5f7-112">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="1e5f7-113">Указывает, что [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) функция должна возвращать путь в глобальном кэше сборок для среды CLR версии 4.</span><span class="sxs-lookup"><span data-stu-id="1e5f7-113">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="1e5f7-114">Значение только в контексте вызова [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="1e5f7-114">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e5f7-115">Требования</span><span class="sxs-lookup"><span data-stu-id="1e5f7-115">Requirements</span></span>  
 <span data-ttu-id="1e5f7-116">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e5f7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e5f7-117">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1e5f7-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1e5f7-118">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e5f7-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e5f7-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e5f7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e5f7-120">См. также</span><span class="sxs-lookup"><span data-stu-id="1e5f7-120">See Also</span></span>  
 [<span data-ttu-id="1e5f7-121">Функция GetCachePath</span><span class="sxs-lookup"><span data-stu-id="1e5f7-121">GetCachePath Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 [<span data-ttu-id="1e5f7-122">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="1e5f7-122">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 [<span data-ttu-id="1e5f7-123">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="1e5f7-123">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
