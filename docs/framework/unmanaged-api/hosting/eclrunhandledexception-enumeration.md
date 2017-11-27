---
title: "Перечисление EClrUnhandledException"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrUnhandledException
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrUnhandledException
helpviewer_keywords: EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 67787072779e0cb22a339c2d13c972ba36f3ed61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="f566f-102">Перечисление EClrUnhandledException</span><span class="sxs-lookup"><span data-stu-id="f566f-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="f566f-103">Описывает доступные параметры для управления исключениями, которые обрабатываются в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="f566f-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f566f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f566f-104">Syntax</span></span>  
  
```  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="f566f-105">Члены</span><span class="sxs-lookup"><span data-stu-id="f566f-105">Members</span></span>  
  
|<span data-ttu-id="f566f-106">Член</span><span class="sxs-lookup"><span data-stu-id="f566f-106">Member</span></span>|<span data-ttu-id="f566f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f566f-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="f566f-108">Указывает, что используется поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f566f-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="f566f-109">Процесс завершен.</span><span class="sxs-lookup"><span data-stu-id="f566f-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="f566f-110">Указывает, что игнорирует необработанные исключения общеязыковой среды выполнения (CLR) и позволяет узлу определить никаких дальнейших действий.</span><span class="sxs-lookup"><span data-stu-id="f566f-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f566f-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f566f-111">Remarks</span></span>  
 <span data-ttu-id="f566f-112">Чтобы указать, что среда CLR аналогично поведению более ранних версий, используйте `eHostDeterminedPolicy` член.</span><span class="sxs-lookup"><span data-stu-id="f566f-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f566f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f566f-113">Requirements</span></span>  
 <span data-ttu-id="f566f-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f566f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f566f-115">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f566f-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f566f-116">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f566f-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f566f-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f566f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f566f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f566f-118">See Also</span></span>  
 [<span data-ttu-id="f566f-119">EClrFailure-перечисление</span><span class="sxs-lookup"><span data-stu-id="f566f-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="f566f-120">EClrOperation-перечисление</span><span class="sxs-lookup"><span data-stu-id="f566f-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="f566f-121">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f566f-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="f566f-122">Setunhandledexceptionpolicy-метод</span><span class="sxs-lookup"><span data-stu-id="f566f-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)  
 [<span data-ttu-id="f566f-123">IHostPolicyManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f566f-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="f566f-124">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="f566f-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
