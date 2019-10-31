---
title: Перечисление EApiCategories
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
ms.openlocfilehash: 0fd9409a5157e1013365c94f01631f130a76f54b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131217"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="7e905-102">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="7e905-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="7e905-103">Описывает категории возможностей, которые узел может блокировать при выполнении в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="7e905-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e905-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e905-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a><span data-ttu-id="7e905-105">Члены</span><span class="sxs-lookup"><span data-stu-id="7e905-105">Members</span></span>  
  
|<span data-ttu-id="7e905-106">Член</span><span class="sxs-lookup"><span data-stu-id="7e905-106">Member</span></span>|<span data-ttu-id="7e905-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7e905-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="7e905-108">Указывает, что все управляемые классы и члены, охваченные другими `EApiCategories` полями, будут заблокированы в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="7e905-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="7e905-109">Указывает, что управляемые классы и члены, разрешающие создание, обработку и уничтожение внешних процессов, блокируются в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="7e905-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="7e905-110">Указывает, что управляемые классы и члены, которые позволяют блокировать создание, обработку и уничтожение внешних потоков, должны быть заблокированы в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="7e905-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="7e905-111">Указывает, что управляемые типы и члены, которые могут привести к утечке памяти при прерывании, блокируются в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="7e905-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="7e905-112">Указывает, что ни одна из категорий управляемого кода не будет заблокирована в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="7e905-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="7e905-113">Указывает, что инфраструктура безопасности среды CLR должна быть заблокирована для частично доверенного кода.</span><span class="sxs-lookup"><span data-stu-id="7e905-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="7e905-114">Указывает, что управляемые классы и члены, возможности которых могут повлиять на работу размещенного процесса, должны быть заблокированы в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="7e905-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="7e905-115">Указывает, что управляемые классы и члены, возможности которых могут влиять на потоки в размещенном процессе, блокируются в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="7e905-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="7e905-116">Указывает, что управляемые классы и члены, которые предоставляют общее состояние, будут заблокированы для выполнения в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="7e905-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="7e905-117">Указывает, что классы и члены среды CLR, которые позволяют коду пользователя удерживать блокировки, блокируются в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="7e905-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="7e905-118">Указывает, что управляемые классы и члены, которые разрешают или запрашивать взаимодействие с пользователем, блокируются в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="7e905-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e905-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="7e905-119">Remarks</span></span>  
 <span data-ttu-id="7e905-120">Метод [иклрхостпротектионманажер:: SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) принимает параметр типа `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="7e905-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="7e905-121">Перечисление `EApiCategories` и метод `SetProtectedCategories` напрямую связаны с управляемым классом <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e905-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="7e905-122">Управляемый класс используется с перечислением <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType>, значения которого непосредственно соответствуют значениям `EApiCategories`, чтобы пометить управляемые типы и члены, которые предоставляют возможности, соответствующие категориям, описанным `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="7e905-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e905-123">Требования</span><span class="sxs-lookup"><span data-stu-id="7e905-123">Requirements</span></span>  
 <span data-ttu-id="7e905-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e905-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e905-125">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7e905-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e905-126">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7e905-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e905-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e905-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e905-128">См. также</span><span class="sxs-lookup"><span data-stu-id="7e905-128">See also</span></span>

- [<span data-ttu-id="7e905-129">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="7e905-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="7e905-130">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="7e905-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
