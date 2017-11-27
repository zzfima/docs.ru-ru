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
ms.openlocfilehash: 372b2466baaa76ba47a6710447d93f9fa6bb967f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="79af4-102">Кокласс CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="79af4-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="79af4-103">Предоставляет интерфейсы для выполнения управляемого кода средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="79af4-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79af4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79af4-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="79af4-105">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="79af4-105">Interfaces</span></span>  
  
|<span data-ttu-id="79af4-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="79af4-106">Interface</span></span>|<span data-ttu-id="79af4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="79af4-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="79af4-108">ICLRRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="79af4-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="79af4-109">Предоставляет методы для управления выполнением приложения средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="79af4-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="79af4-110">ICLRValidator-интерфейс</span><span class="sxs-lookup"><span data-stu-id="79af4-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="79af4-111">Предоставляет методы для проверки переносимого исполняемого образа, а также для подробных отчетов об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="79af4-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="79af4-112">Требования</span><span class="sxs-lookup"><span data-stu-id="79af4-112">Requirements</span></span>  
 <span data-ttu-id="79af4-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79af4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79af4-114">**Заголовок:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="79af4-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="79af4-115">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="79af4-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="79af4-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79af4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79af4-117">См. также</span><span class="sxs-lookup"><span data-stu-id="79af4-117">See Also</span></span>  
 [<span data-ttu-id="79af4-118">Размещение компонентных классов</span><span class="sxs-lookup"><span data-stu-id="79af4-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
