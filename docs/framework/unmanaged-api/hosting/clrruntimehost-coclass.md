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
ms.openlocfilehash: 841b05ca1037d82046820554878d883f94687d34
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779144"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="54274-102">Кокласс CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="54274-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="54274-103">Предоставляет интерфейсы для выполнения управляемого кода средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="54274-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54274-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54274-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="54274-105">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="54274-105">Interfaces</span></span>  
  
|<span data-ttu-id="54274-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="54274-106">Interface</span></span>|<span data-ttu-id="54274-107">Описание</span><span class="sxs-lookup"><span data-stu-id="54274-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="54274-108">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="54274-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="54274-109">Предоставляет методы для управления выполнением приложений средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="54274-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="54274-110">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="54274-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="54274-111">Предоставляет методы для проверки переносимого исполняемого образа и подробные отчеты об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="54274-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54274-112">Требования</span><span class="sxs-lookup"><span data-stu-id="54274-112">Requirements</span></span>  
 <span data-ttu-id="54274-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54274-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54274-114">**Заголовок.** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="54274-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="54274-115">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="54274-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54274-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54274-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54274-117">См. также</span><span class="sxs-lookup"><span data-stu-id="54274-117">See also</span></span>

- [<span data-ttu-id="54274-118">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="54274-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
