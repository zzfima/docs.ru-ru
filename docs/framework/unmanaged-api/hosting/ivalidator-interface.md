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
ms.openlocfilehash: 2f516bf1f19e4d4a77e2d6af834a1c3d4e34c327
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121918"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="87d76-102">Интерфейс IValidator</span><span class="sxs-lookup"><span data-stu-id="87d76-102">IValidator Interface</span></span>
<span data-ttu-id="87d76-103">Предоставляет методы для проверки переносимого исполняемого (PE) образа и сообщение об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="87d76-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87d76-104">Методы</span><span class="sxs-lookup"><span data-stu-id="87d76-104">Methods</span></span>  
  
|<span data-ttu-id="87d76-105">Метод</span><span class="sxs-lookup"><span data-stu-id="87d76-105">Method</span></span>|<span data-ttu-id="87d76-106">Описание</span><span class="sxs-lookup"><span data-stu-id="87d76-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="87d76-107">Validate</span><span class="sxs-lookup"><span data-stu-id="87d76-107">Validate</span></span>|<span data-ttu-id="87d76-108">Проверяет указанный промежуточного языка MSIL файл PE или Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="87d76-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="87d76-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="87d76-109">FormatEventInfo</span></span>|<span data-ttu-id="87d76-110">Получает сообщение об ошибке, соответствующее указанной ошибкой проверки.</span><span class="sxs-lookup"><span data-stu-id="87d76-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87d76-111">Требования</span><span class="sxs-lookup"><span data-stu-id="87d76-111">Requirements</span></span>  
 <span data-ttu-id="87d76-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87d76-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87d76-113">**Заголовок.** IValidator.idl в файле IValidator.h</span><span class="sxs-lookup"><span data-stu-id="87d76-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="87d76-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87d76-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87d76-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87d76-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d76-116">См. также</span><span class="sxs-lookup"><span data-stu-id="87d76-116">See also</span></span>

- [<span data-ttu-id="87d76-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="87d76-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="87d76-118">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="87d76-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
