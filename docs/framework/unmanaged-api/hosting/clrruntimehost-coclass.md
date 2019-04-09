---
title: Кокласс CLRRuntimeHost
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bae2d134c412023d0f126453b5285662d994c78
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207764"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="bd2f5-102">Кокласс CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="bd2f5-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="bd2f5-103">Предоставляет интерфейсы для выполнения управляемого кода средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd2f5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd2f5-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="bd2f5-105">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="bd2f5-105">Interfaces</span></span>  
  
|<span data-ttu-id="bd2f5-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="bd2f5-106">Interface</span></span>|<span data-ttu-id="bd2f5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bd2f5-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="bd2f5-108">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="bd2f5-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="bd2f5-109">Предоставляет методы для управления выполнением приложений средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="bd2f5-110">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="bd2f5-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="bd2f5-111">Предоставляет методы для проверки переносимого исполняемого образа и подробные отчеты об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="bd2f5-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd2f5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bd2f5-112">Requirements</span></span>  
 <span data-ttu-id="bd2f5-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd2f5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd2f5-114">**Заголовок.** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="bd2f5-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="bd2f5-115">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd2f5-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="bd2f5-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bd2f5-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bd2f5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bd2f5-117">See also</span></span>

- [<span data-ttu-id="bd2f5-118">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="bd2f5-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
