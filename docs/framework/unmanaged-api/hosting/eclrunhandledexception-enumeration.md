---
title: Перечисление EClrUnhandledException
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e5fb3ab1d2dedb220fd4a486409512414233021
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795976"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="eee5b-102">Перечисление EClrUnhandledException</span><span class="sxs-lookup"><span data-stu-id="eee5b-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="eee5b-103">Описывает доступные параметры для управления исключениями, которые не обрабатываются в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="eee5b-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eee5b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eee5b-104">Syntax</span></span>  
  
```  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="eee5b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="eee5b-105">Members</span></span>  
  
|<span data-ttu-id="eee5b-106">Член</span><span class="sxs-lookup"><span data-stu-id="eee5b-106">Member</span></span>|<span data-ttu-id="eee5b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="eee5b-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="eee5b-108">Указывает, что используется поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eee5b-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="eee5b-109">Процесс завершен.</span><span class="sxs-lookup"><span data-stu-id="eee5b-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="eee5b-110">Указывает, что среда CLR (CLR) не учитывает необработанные исключения и позволяет узлу определить дальнейшие действия.</span><span class="sxs-lookup"><span data-stu-id="eee5b-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eee5b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="eee5b-111">Remarks</span></span>  
 <span data-ttu-id="eee5b-112">Чтобы указать, что среда CLR аналогично поведению более ранних версий, используйте `eHostDeterminedPolicy` член.</span><span class="sxs-lookup"><span data-stu-id="eee5b-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eee5b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="eee5b-113">Requirements</span></span>  
 <span data-ttu-id="eee5b-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eee5b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eee5b-115">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eee5b-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eee5b-116">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eee5b-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eee5b-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eee5b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee5b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="eee5b-118">See also</span></span>

- [<span data-ttu-id="eee5b-119">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="eee5b-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="eee5b-120">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="eee5b-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="eee5b-121">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="eee5b-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="eee5b-122">Метод SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="eee5b-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="eee5b-123">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="eee5b-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="eee5b-124">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="eee5b-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
