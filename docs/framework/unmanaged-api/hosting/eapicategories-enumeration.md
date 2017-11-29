---
title: "Перечисление EApiCategories"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EApiCategories
api_location: mscoree.dll
api_type: COM
f1_keywords: EApiCategories
helpviewer_keywords: EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eaff0133020fe84e58f8a130bffc8ddc2a55a19d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="c4042-102">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="c4042-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="c4042-103">Описывает категории возможностей, которые узел может блокировать при выполнении в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="c4042-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4042-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4042-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c4042-105">Члены</span><span class="sxs-lookup"><span data-stu-id="c4042-105">Members</span></span>  
  
|<span data-ttu-id="c4042-106">Член</span><span class="sxs-lookup"><span data-stu-id="c4042-106">Member</span></span>|<span data-ttu-id="c4042-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c4042-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="c4042-108">Указывает, что все управляемые классы и члены, которые рассматриваются другими `EApiCategories` поля будет блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="c4042-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="c4042-109">Указывает, что управляемых классов и членов, которые позволяют создания, изменения и удаления из внешних процессов блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="c4042-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="c4042-110">Указывает, что управляемые классы и члены, позволяющие создания, изменения и удаления внешние потоки блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="c4042-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="c4042-111">Указывает, что управляемые типы и члены, которые потенциально могут вызвать утечку памяти при прерывании блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="c4042-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="c4042-112">Указывает, что категории управляемого кода не будет блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="c4042-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="c4042-113">Блокировка инфраструктуру безопасности среды выполнения (CLR) от использования кодом с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="c4042-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="c4042-114">Указывает, что управляемых классов и членов, возможности которых могут повлиять на размещенный процесс блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="c4042-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="c4042-115">Указывает, что управляемых классов и членов, возможности которых могут повлиять на потоки в размещенном процессе блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="c4042-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="c4042-116">Указывает, заблокирован управляемых классов и членов, которые предоставляют общее состояние при выполнении в частично доверенный код.</span><span class="sxs-lookup"><span data-stu-id="c4042-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="c4042-117">Указывает, что общие классы CLR и члены, позволяющие код для удержания блокировок блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="c4042-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="c4042-118">Указывает, что управляемых классов и членов, которые разрешают или требующих такого взаимодействия блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="c4042-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4042-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4042-119">Remarks</span></span>  
 <span data-ttu-id="c4042-120">[ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) метод принимает параметр типа `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="c4042-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="c4042-121">`EApiCategories` Перечисления и `SetProtectedCategories` метод непосредственно связаны в управляемом <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="c4042-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="c4042-122">Управляемый класс используется с <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> перечисления, значения которого соответствуют непосредственно `EApiCategories` значения, чтобы пометить управляемых типов и членов, которые предоставляют возможности, соответствующие категориям, описываемого `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="c4042-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4042-123">Требования</span><span class="sxs-lookup"><span data-stu-id="c4042-123">Requirements</span></span>  
 <span data-ttu-id="c4042-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4042-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4042-125">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c4042-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4042-126">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c4042-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4042-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4042-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4042-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c4042-128">See Also</span></span>  
 [<span data-ttu-id="c4042-129">Iclrhostprotectionmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c4042-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="c4042-130">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="c4042-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
