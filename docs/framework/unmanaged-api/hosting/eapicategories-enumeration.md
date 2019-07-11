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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41513d9b6f98743bfad95e4d9606cfb4927369e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769791"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="b0356-102">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="b0356-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="b0356-103">Описывает категории возможностей, которые узел может блокировать при выполнении в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b0356-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0356-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0356-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b0356-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b0356-105">Members</span></span>  
  
|<span data-ttu-id="b0356-106">Член</span><span class="sxs-lookup"><span data-stu-id="b0356-106">Member</span></span>|<span data-ttu-id="b0356-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b0356-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="b0356-108">Указывает, что все управляемые классы и члены, которые покрыты другие `EApiCategories` поля будет блокироваться в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b0356-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="b0356-109">Указывает, что управляемые классы и члены, позволяющие создания, обработки и деструкция внешних процессов заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b0356-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="b0356-110">Указывает, что управляемые классы и члены, позволяющие создания, обработки и уничтожение потоков внешних заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b0356-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="b0356-111">Указывает, что управляемые типы и члены, которые потенциально могут привести к утечке памяти при прерывании работы заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b0356-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="b0356-112">Указывает, что категории управляемого кода не будет блокироваться в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b0356-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="b0356-113">Указывает, что заблокирован инфраструктуре безопасности среды выполнения (CLR) не могут использоваться частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b0356-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="b0356-114">Указывает, что управляемых классов и членов, возможности которых могут повлиять на размещенный процесс заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b0356-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="b0356-115">Указывает, что выполнение управляемых классов и членов, возможности которых могут повлиять на потоки в размещенном процессе будет блокироваться в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b0356-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="b0356-116">Указывает, что управляемые классы и члены, предоставляющие доступ к общему состоянию заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b0356-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="b0356-117">Указывает, что общие классы CLR и члены, позволяющие код для удержания блокировок заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b0356-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="b0356-118">Указывает, что управляемых классов и членов, которые разрешают или требуется участие пользователя заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b0356-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0356-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="b0356-119">Remarks</span></span>  
 <span data-ttu-id="b0356-120">[ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) метод принимает параметр типа `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="b0356-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="b0356-121">`EApiCategories` Перечисления и `SetProtectedCategories` метод непосредственно связаны в управляемый <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="b0356-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="b0356-122">Управляемый класс используется с <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> перечисления, значения которых соответствуют `EApiCategories` значения, чтобы пометить управляемых типов и членов, которые предоставляют возможности, соответствующие категории, описанные по `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="b0356-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0356-123">Требования</span><span class="sxs-lookup"><span data-stu-id="b0356-123">Requirements</span></span>  
 <span data-ttu-id="b0356-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0356-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0356-125">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b0356-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b0356-126">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0356-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0356-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0356-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0356-128">См. также</span><span class="sxs-lookup"><span data-stu-id="b0356-128">See also</span></span>

- [<span data-ttu-id="b0356-129">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="b0356-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="b0356-130">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="b0356-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
