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
ms.openlocfilehash: f25348410387a7b0e03ef897e8534336baeb126a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432213"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="28f49-102">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="28f49-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="28f49-103">Описывает категории возможностей, которые узел может блокировать при выполнении в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="28f49-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28f49-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28f49-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="28f49-105">Участники</span><span class="sxs-lookup"><span data-stu-id="28f49-105">Members</span></span>  
  
|<span data-ttu-id="28f49-106">Член</span><span class="sxs-lookup"><span data-stu-id="28f49-106">Member</span></span>|<span data-ttu-id="28f49-107">Описание</span><span class="sxs-lookup"><span data-stu-id="28f49-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="28f49-108">Указывает, что все управляемые классы и члены, которые рассматриваются другими `EApiCategories` поля будет блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="28f49-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="28f49-109">Указывает, что управляемых классов и членов, которые позволяют создания, изменения и удаления из внешних процессов блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="28f49-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="28f49-110">Указывает, что управляемые классы и члены, позволяющие создания, изменения и удаления внешние потоки блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="28f49-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="28f49-111">Указывает, что управляемые типы и члены, которые потенциально могут вызвать утечку памяти при прерывании блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="28f49-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="28f49-112">Указывает, что категории управляемого кода не будет блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="28f49-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="28f49-113">Блокировка инфраструктуру безопасности среды выполнения (CLR) от использования кодом с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="28f49-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="28f49-114">Указывает, что управляемых классов и членов, возможности которых могут повлиять на размещенный процесс блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="28f49-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="28f49-115">Указывает, что управляемых классов и членов, возможности которых могут повлиять на потоки в размещенном процессе блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="28f49-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="28f49-116">Указывает, заблокирован управляемых классов и членов, которые предоставляют общее состояние при выполнении в частично доверенный код.</span><span class="sxs-lookup"><span data-stu-id="28f49-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="28f49-117">Указывает, что общие классы CLR и члены, позволяющие код для удержания блокировок блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="28f49-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="28f49-118">Указывает, что управляемых классов и членов, которые разрешают или требующих такого взаимодействия блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="28f49-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28f49-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="28f49-119">Remarks</span></span>  
 <span data-ttu-id="28f49-120">[ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) метод принимает параметр типа `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="28f49-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="28f49-121">`EApiCategories` Перечисления и `SetProtectedCategories` метод непосредственно связаны в управляемом <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="28f49-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="28f49-122">Управляемый класс используется с <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> перечисления, значения которого соответствуют непосредственно `EApiCategories` значения, чтобы пометить управляемых типов и членов, которые предоставляют возможности, соответствующие категориям, описываемого `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="28f49-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28f49-123">Требования</span><span class="sxs-lookup"><span data-stu-id="28f49-123">Requirements</span></span>  
 <span data-ttu-id="28f49-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28f49-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28f49-125">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="28f49-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28f49-126">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28f49-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28f49-127">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28f49-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f49-128">См. также</span><span class="sxs-lookup"><span data-stu-id="28f49-128">See Also</span></span>  
 [<span data-ttu-id="28f49-129">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="28f49-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="28f49-130">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="28f49-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
