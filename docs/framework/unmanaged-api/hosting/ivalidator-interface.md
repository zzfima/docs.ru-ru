---
title: "Интерфейс IValidator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1afa255fa0b1baec35dbd8aa6e0beef62d240c31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ivalidator-interface"></a><span data-ttu-id="bd81e-102">Интерфейс IValidator</span><span class="sxs-lookup"><span data-stu-id="bd81e-102">IValidator Interface</span></span>
<span data-ttu-id="bd81e-103">Предоставляет методы для проверки переносимого исполняемого (PE) образа и возврат ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="bd81e-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bd81e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="bd81e-104">Methods</span></span>  
  
|<span data-ttu-id="bd81e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="bd81e-105">Method</span></span>|<span data-ttu-id="bd81e-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="bd81e-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="bd81e-107">Validate</span><span class="sxs-lookup"><span data-stu-id="bd81e-107">Validate</span></span>|<span data-ttu-id="bd81e-108">Проверяет указанный файл промежуточного языка MSIL PE или корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bd81e-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="bd81e-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="bd81e-109">FormatEventInfo</span></span>|<span data-ttu-id="bd81e-110">Возвращает сообщение об ошибке, соответствующее указанной ошибкой проверки.</span><span class="sxs-lookup"><span data-stu-id="bd81e-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd81e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bd81e-111">Requirements</span></span>  
 <span data-ttu-id="bd81e-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd81e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd81e-113">**Заголовок:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="bd81e-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="bd81e-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd81e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd81e-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd81e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd81e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bd81e-116">See Also</span></span>  
 [<span data-ttu-id="bd81e-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="bd81e-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="bd81e-118">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="bd81e-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
