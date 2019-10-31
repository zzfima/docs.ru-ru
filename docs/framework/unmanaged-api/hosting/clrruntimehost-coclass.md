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
ms.openlocfilehash: b1e595e1a4f1b462437f47207b998829a8bd774d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129453"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="25241-102">Кокласс CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="25241-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="25241-103">Предоставляет интерфейсы для управления выполнением кода средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="25241-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25241-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25241-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="25241-105">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="25241-105">Interfaces</span></span>  
  
|<span data-ttu-id="25241-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="25241-106">Interface</span></span>|<span data-ttu-id="25241-107">Описание</span><span class="sxs-lookup"><span data-stu-id="25241-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="25241-108">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="25241-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="25241-109">Предоставляет методы для управления выполнением приложений средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="25241-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="25241-110">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="25241-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="25241-111">Предоставляет методы для проверки переносимых исполняемых образов и для подробных отчетов об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="25241-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="25241-112">Требования</span><span class="sxs-lookup"><span data-stu-id="25241-112">Requirements</span></span>  
 <span data-ttu-id="25241-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25241-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25241-114">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="25241-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="25241-115">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="25241-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25241-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25241-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25241-117">См. также</span><span class="sxs-lookup"><span data-stu-id="25241-117">See also</span></span>

- [<span data-ttu-id="25241-118">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="25241-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
