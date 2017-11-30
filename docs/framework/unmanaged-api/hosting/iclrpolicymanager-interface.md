---
title: "Интерфейс ICLRPolicyManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager
helpviewer_keywords: ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f3dd904184b730a5b0f5b2dfcac4197e708544d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="96308-102">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="96308-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="96308-103">Предоставляет методы, позволяющие основному приложению задать действия политики, которые необходимо выполнить в случае сбоев и увеличение времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="96308-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96308-104">Методы</span><span class="sxs-lookup"><span data-stu-id="96308-104">Methods</span></span>  
  
|<span data-ttu-id="96308-105">Метод</span><span class="sxs-lookup"><span data-stu-id="96308-105">Method</span></span>|<span data-ttu-id="96308-106">Описание</span><span class="sxs-lookup"><span data-stu-id="96308-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="96308-107">SetActionOnFailure-метод</span><span class="sxs-lookup"><span data-stu-id="96308-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="96308-108">Задает действие политики, которое должен выполнить общеязыковой среды выполнения (CLR), если указанного сбоя.</span><span class="sxs-lookup"><span data-stu-id="96308-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="96308-109">SetActionOnTimeout-метод</span><span class="sxs-lookup"><span data-stu-id="96308-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="96308-110">Задает действие политики, которое должна выполнять среда CLR при истечении времени ожидания заданной операции.</span><span class="sxs-lookup"><span data-stu-id="96308-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="96308-111">Setdefaultaction-метод</span><span class="sxs-lookup"><span data-stu-id="96308-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="96308-112">Задает действие политики, которое должна выполнять среда CLR при возникновении указанной операции.</span><span class="sxs-lookup"><span data-stu-id="96308-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="96308-113">SetTimeout-метод</span><span class="sxs-lookup"><span data-stu-id="96308-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="96308-114">Задает значение времени ожидания для указанной операции.</span><span class="sxs-lookup"><span data-stu-id="96308-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="96308-115">Settimeoutandaction-метод</span><span class="sxs-lookup"><span data-stu-id="96308-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="96308-116">Задает значение времени ожидания для указанной операции и определяет действие политики, которое должна выполнять среда CLR при выполнении этой операции.</span><span class="sxs-lookup"><span data-stu-id="96308-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="96308-117">Setunhandledexceptionpolicy-метод</span><span class="sxs-lookup"><span data-stu-id="96308-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="96308-118">Определяет поведение среды CLR при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="96308-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96308-119">Требования</span><span class="sxs-lookup"><span data-stu-id="96308-119">Requirements</span></span>  
 <span data-ttu-id="96308-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96308-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96308-121">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="96308-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96308-122">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="96308-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96308-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96308-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96308-124">См. также</span><span class="sxs-lookup"><span data-stu-id="96308-124">See Also</span></span>  
 [<span data-ttu-id="96308-125">EClrFailure-перечисление</span><span class="sxs-lookup"><span data-stu-id="96308-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="96308-126">EClrOperation-перечисление</span><span class="sxs-lookup"><span data-stu-id="96308-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="96308-127">EPolicyAction-перечисление</span><span class="sxs-lookup"><span data-stu-id="96308-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="96308-128">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="96308-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
