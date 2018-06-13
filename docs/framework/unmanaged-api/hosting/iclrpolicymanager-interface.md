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
ms.openlocfilehash: 8e8a1b1bcf4470f5e754775b1137b8221ae1d0b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435151"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="ea6f6-102">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="ea6f6-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="ea6f6-103">Предоставляет методы, позволяющие основному приложению задать действия политики, которые необходимо выполнить в случае сбоев и увеличение времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="ea6f6-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ea6f6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ea6f6-104">Methods</span></span>  
  
|<span data-ttu-id="ea6f6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ea6f6-105">Method</span></span>|<span data-ttu-id="ea6f6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ea6f6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ea6f6-107">Метод SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="ea6f6-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="ea6f6-108">Задает действие политики, которое должен выполнить общеязыковой среды выполнения (CLR), если указанного сбоя.</span><span class="sxs-lookup"><span data-stu-id="ea6f6-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="ea6f6-109">Метод SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="ea6f6-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="ea6f6-110">Задает действие политики, которое должна выполнять среда CLR при истечении времени ожидания заданной операции.</span><span class="sxs-lookup"><span data-stu-id="ea6f6-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="ea6f6-111">Метод SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="ea6f6-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="ea6f6-112">Задает действие политики, которое должна выполнять среда CLR при возникновении указанной операции.</span><span class="sxs-lookup"><span data-stu-id="ea6f6-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="ea6f6-113">Метод SetTimeout</span><span class="sxs-lookup"><span data-stu-id="ea6f6-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="ea6f6-114">Задает значение времени ожидания для указанной операции.</span><span class="sxs-lookup"><span data-stu-id="ea6f6-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="ea6f6-115">Метод SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="ea6f6-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="ea6f6-116">Задает значение времени ожидания для указанной операции и определяет действие политики, которое должна выполнять среда CLR при выполнении этой операции.</span><span class="sxs-lookup"><span data-stu-id="ea6f6-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="ea6f6-117">Метод SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="ea6f6-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="ea6f6-118">Определяет поведение среды CLR при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="ea6f6-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea6f6-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ea6f6-119">Requirements</span></span>  
 <span data-ttu-id="ea6f6-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea6f6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea6f6-121">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ea6f6-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea6f6-122">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea6f6-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea6f6-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea6f6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea6f6-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ea6f6-124">See Also</span></span>  
 [<span data-ttu-id="ea6f6-125">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="ea6f6-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="ea6f6-126">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="ea6f6-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="ea6f6-127">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="ea6f6-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="ea6f6-128">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="ea6f6-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
