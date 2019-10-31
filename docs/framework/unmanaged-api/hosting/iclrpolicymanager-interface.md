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
ms.openlocfilehash: 59aa904d4c67326b60381d3476eaab179d7fa42b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140808"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="c856f-102">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="c856f-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="c856f-103">Предоставляет методы, позволяющие основному приложению указывать действия политики, выполняемые в случае сбоев и истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="c856f-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c856f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c856f-104">Methods</span></span>  
  
|<span data-ttu-id="c856f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c856f-105">Method</span></span>|<span data-ttu-id="c856f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c856f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c856f-107">Метод SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="c856f-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="c856f-108">Указывает действие политики, которое должна выполнять среда CLR при возникновении указанного сбоя.</span><span class="sxs-lookup"><span data-stu-id="c856f-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="c856f-109">Метод SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="c856f-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="c856f-110">Указывает действие политики, которое должна выполнять среда CLR при истечении времени ожидания указанной операции.</span><span class="sxs-lookup"><span data-stu-id="c856f-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="c856f-111">Метод SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="c856f-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="c856f-112">Указывает действие политики, которое должна выполнять среда CLR при выполнении указанной операции.</span><span class="sxs-lookup"><span data-stu-id="c856f-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="c856f-113">Метод SetTimeout</span><span class="sxs-lookup"><span data-stu-id="c856f-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="c856f-114">Задает значение времени ожидания для указанной операции.</span><span class="sxs-lookup"><span data-stu-id="c856f-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="c856f-115">Метод SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="c856f-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="c856f-116">Задает значение времени ожидания для указанной операции и указывает действие политики, которое должна выполнять среда CLR при выполнении операции.</span><span class="sxs-lookup"><span data-stu-id="c856f-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="c856f-117">Метод SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="c856f-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="c856f-118">Задает поведение среды CLR при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="c856f-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c856f-119">Требования</span><span class="sxs-lookup"><span data-stu-id="c856f-119">Requirements</span></span>  
 <span data-ttu-id="c856f-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c856f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c856f-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c856f-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c856f-122">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c856f-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c856f-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c856f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c856f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c856f-124">See also</span></span>

- [<span data-ttu-id="c856f-125">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="c856f-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="c856f-126">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="c856f-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="c856f-127">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="c856f-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="c856f-128">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="c856f-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
