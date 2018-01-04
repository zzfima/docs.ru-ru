---
title: "Кокласс CLRRuntimeHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CLRRuntimeHost
helpviewer_keywords: CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 18e4518a2e321609a8add06c399ed9588748d1ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="a437a-102">Кокласс CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a437a-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="a437a-103">Предоставляет интерфейсы для выполнения управляемого кода средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="a437a-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a437a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a437a-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="a437a-105">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="a437a-105">Interfaces</span></span>  
  
|<span data-ttu-id="a437a-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="a437a-106">Interface</span></span>|<span data-ttu-id="a437a-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="a437a-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="a437a-108">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a437a-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="a437a-109">Предоставляет методы для управления выполнением приложения средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="a437a-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="a437a-110">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="a437a-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="a437a-111">Предоставляет методы для проверки переносимого исполняемого образа, а также для подробных отчетов об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="a437a-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a437a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="a437a-112">Requirements</span></span>  
 <span data-ttu-id="a437a-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a437a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a437a-114">**Заголовок:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="a437a-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="a437a-115">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a437a-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a437a-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a437a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a437a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a437a-117">See Also</span></span>  
 [<span data-ttu-id="a437a-118">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="a437a-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
