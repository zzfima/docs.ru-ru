---
title: "Интерфейс IValidator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IValidator
api_location: mscoree.dll
api_type: COM
f1_keywords: IValidator
helpviewer_keywords: IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7d88bfa0a3e71f34a7439e97f4347a06aa2c4058
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ivalidator-interface"></a><span data-ttu-id="95d7e-102">Интерфейс IValidator</span><span class="sxs-lookup"><span data-stu-id="95d7e-102">IValidator Interface</span></span>
<span data-ttu-id="95d7e-103">Предоставляет методы для проверки переносимого исполняемого (PE) образа и возврат ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="95d7e-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95d7e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="95d7e-104">Methods</span></span>  
  
|<span data-ttu-id="95d7e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="95d7e-105">Method</span></span>|<span data-ttu-id="95d7e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="95d7e-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="95d7e-107">Validate</span><span class="sxs-lookup"><span data-stu-id="95d7e-107">Validate</span></span>|<span data-ttu-id="95d7e-108">Проверяет указанный файл промежуточного языка MSIL PE или корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="95d7e-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="95d7e-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="95d7e-109">FormatEventInfo</span></span>|<span data-ttu-id="95d7e-110">Возвращает сообщение об ошибке, соответствующее указанной ошибкой проверки.</span><span class="sxs-lookup"><span data-stu-id="95d7e-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95d7e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="95d7e-111">Requirements</span></span>  
 <span data-ttu-id="95d7e-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95d7e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95d7e-113">**Заголовок:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="95d7e-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="95d7e-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95d7e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95d7e-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95d7e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95d7e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="95d7e-116">See Also</span></span>  
 [<span data-ttu-id="95d7e-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="95d7e-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="95d7e-118">Компонентный класс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="95d7e-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
