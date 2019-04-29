---
title: Интерфейс ICLRPolicyManager
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2eeccc4dfd7a7147fe791444eeeca2bd3a844305
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638870"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="6f29a-102">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="6f29a-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="6f29a-103">Предоставляет методы, позволяющие основному приложению задать политику действий, выполняемых в случае сбоев и использование времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="6f29a-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6f29a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6f29a-104">Methods</span></span>  
  
|<span data-ttu-id="6f29a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6f29a-105">Method</span></span>|<span data-ttu-id="6f29a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6f29a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6f29a-107">Метод SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="6f29a-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="6f29a-108">Задает действие политики, которые общеязыковой среды выполнения (CLR) необходимо выполнить при возникновении указанной ошибки.</span><span class="sxs-lookup"><span data-stu-id="6f29a-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="6f29a-109">Метод SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="6f29a-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="6f29a-110">Указывает действие политики, которое должна выполнять среда CLR, после истечения указанного времени ожидания операции.</span><span class="sxs-lookup"><span data-stu-id="6f29a-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="6f29a-111">Метод SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="6f29a-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="6f29a-112">Указывает действие политики, которое должна выполнять среда CLR при возникновении указанной операции.</span><span class="sxs-lookup"><span data-stu-id="6f29a-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="6f29a-113">Метод SetTimeout</span><span class="sxs-lookup"><span data-stu-id="6f29a-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="6f29a-114">Задает значение времени ожидания для указанной операции.</span><span class="sxs-lookup"><span data-stu-id="6f29a-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="6f29a-115">Метод SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="6f29a-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="6f29a-116">Задает значение времени ожидания для указанной операции и указывает действие политики, которое должна выполнять среда CLR при выполнении этой операции.</span><span class="sxs-lookup"><span data-stu-id="6f29a-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="6f29a-117">Метод SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="6f29a-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="6f29a-118">Определяет поведение среды CLR, при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="6f29a-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6f29a-119">Требования</span><span class="sxs-lookup"><span data-stu-id="6f29a-119">Requirements</span></span>  
 <span data-ttu-id="6f29a-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f29a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f29a-121">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6f29a-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f29a-122">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f29a-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f29a-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f29a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f29a-124">См. также</span><span class="sxs-lookup"><span data-stu-id="6f29a-124">See also</span></span>

- [<span data-ttu-id="6f29a-125">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="6f29a-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="6f29a-126">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="6f29a-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="6f29a-127">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="6f29a-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="6f29a-128">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="6f29a-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
