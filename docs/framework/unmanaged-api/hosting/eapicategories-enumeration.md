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
ms.openlocfilehash: 3debd3f13d78841188dd8c900f51c0110e1d4c67
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086459"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="c2b2a-102">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="c2b2a-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="c2b2a-103">Описывает категории возможностей, которые узел может блокировать при выполнении в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2b2a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2b2a-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="c2b2a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c2b2a-105">Members</span></span>  
  
|<span data-ttu-id="c2b2a-106">Член</span><span class="sxs-lookup"><span data-stu-id="c2b2a-106">Member</span></span>|<span data-ttu-id="c2b2a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c2b2a-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="c2b2a-108">Указывает, что все управляемые классы и члены, которые покрыты другие `EApiCategories` поля будет блокироваться в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="c2b2a-109">Указывает, что управляемые классы и члены, позволяющие создания, обработки и деструкция внешних процессов заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="c2b2a-110">Указывает, что управляемые классы и члены, позволяющие создания, обработки и уничтожение потоков внешних заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="c2b2a-111">Указывает, что управляемые типы и члены, которые потенциально могут привести к утечке памяти при прерывании работы заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="c2b2a-112">Указывает, что категории управляемого кода не будет блокироваться в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="c2b2a-113">Указывает, что заблокирован инфраструктуре безопасности среды выполнения (CLR) не могут использоваться частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="c2b2a-114">Указывает, что управляемых классов и членов, возможности которых могут повлиять на размещенный процесс заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="c2b2a-115">Указывает, что выполнение управляемых классов и членов, возможности которых могут повлиять на потоки в размещенном процессе будет блокироваться в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="c2b2a-116">Указывает, что управляемые классы и члены, предоставляющие доступ к общему состоянию заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="c2b2a-117">Указывает, что общие классы CLR и члены, позволяющие код для удержания блокировок заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="c2b2a-118">Указывает, что управляемых классов и членов, которые разрешают или требуется участие пользователя заблокирован для выполнения в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2b2a-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2b2a-119">Remarks</span></span>  
 <span data-ttu-id="c2b2a-120">[ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) метод принимает параметр типа `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="c2b2a-121">`EApiCategories` Перечисления и `SetProtectedCategories` метод непосредственно связаны в управляемый <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="c2b2a-122">Управляемый класс используется с <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> перечисления, значения которых соответствуют `EApiCategories` значения, чтобы пометить управляемых типов и членов, которые предоставляют возможности, соответствующие категории, описанные по `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="c2b2a-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2b2a-123">Требования</span><span class="sxs-lookup"><span data-stu-id="c2b2a-123">Requirements</span></span>  
 <span data-ttu-id="c2b2a-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2b2a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2b2a-125">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2b2a-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2b2a-126">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2b2a-126">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c2b2a-127">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c2b2a-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c2b2a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c2b2a-128">See also</span></span>

- [<span data-ttu-id="c2b2a-129">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="c2b2a-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="c2b2a-130">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="c2b2a-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
