---
title: Интерфейс IValidator
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e79a69bf71aee035fb1f9a0178879d7c19e62b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ivalidator-interface"></a><span data-ttu-id="c72c5-102">Интерфейс IValidator</span><span class="sxs-lookup"><span data-stu-id="c72c5-102">IValidator Interface</span></span>
<span data-ttu-id="c72c5-103">Предоставляет методы для проверки переносимого исполняемого (PE) образа и возврат ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="c72c5-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c72c5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c72c5-104">Methods</span></span>  
  
|<span data-ttu-id="c72c5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c72c5-105">Method</span></span>|<span data-ttu-id="c72c5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c72c5-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c72c5-107">Validate</span><span class="sxs-lookup"><span data-stu-id="c72c5-107">Validate</span></span>|<span data-ttu-id="c72c5-108">Проверяет указанный файл промежуточного языка MSIL PE или корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c72c5-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="c72c5-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="c72c5-109">FormatEventInfo</span></span>|<span data-ttu-id="c72c5-110">Возвращает сообщение об ошибке, соответствующее указанной ошибкой проверки.</span><span class="sxs-lookup"><span data-stu-id="c72c5-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c72c5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c72c5-111">Requirements</span></span>  
 <span data-ttu-id="c72c5-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c72c5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c72c5-113">**Заголовок:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="c72c5-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="c72c5-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c72c5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c72c5-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c72c5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c72c5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c72c5-116">See Also</span></span>  
 [<span data-ttu-id="c72c5-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="c72c5-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="c72c5-118">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c72c5-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
