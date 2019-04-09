---
title: Интерфейс ICLRValidator
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05287d3674e55a87cfe359fc08f74fa46000d79f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075851"
---
# <a name="iclrvalidator-interface"></a><span data-ttu-id="81f8c-102">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="81f8c-102">ICLRValidator Interface</span></span>
<span data-ttu-id="81f8c-103">Предоставляет методы для проверки переносимого исполняемого (PE) образа и сообщение об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="81f8c-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81f8c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="81f8c-104">Methods</span></span>  
  
|<span data-ttu-id="81f8c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="81f8c-105">Method</span></span>|<span data-ttu-id="81f8c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="81f8c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81f8c-107">Метод FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="81f8c-107">FormatEventInfo Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-formateventinfo-method.md)|<span data-ttu-id="81f8c-108">Возвращает подробное сообщение об ошибке проверки указанной.</span><span class="sxs-lookup"><span data-stu-id="81f8c-108">Gets a detailed message about the specified validation error.</span></span>|  
|[<span data-ttu-id="81f8c-109">Метод Validate</span><span class="sxs-lookup"><span data-stu-id="81f8c-109">Validate Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md)|<span data-ttu-id="81f8c-110">Проверяет переносимый исполняемый файл или код промежуточного языка Майкрософт (MSIL) в указанном файле.</span><span class="sxs-lookup"><span data-stu-id="81f8c-110">Validates the portable executable or Microsoft intermediate language (MSIL) in the specified file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81f8c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="81f8c-111">Requirements</span></span>  
 <span data-ttu-id="81f8c-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81f8c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81f8c-113">**Заголовок.** IValidator.idl в файле IValidator.h</span><span class="sxs-lookup"><span data-stu-id="81f8c-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="81f8c-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="81f8c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="81f8c-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="81f8c-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="81f8c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="81f8c-116">See also</span></span>

- [<span data-ttu-id="81f8c-117">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="81f8c-117">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="81f8c-118">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="81f8c-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="81f8c-119">Кокласс CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="81f8c-119">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
