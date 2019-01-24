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
ms.openlocfilehash: 9f307ad5689602b030c609a51f6834bdbb0ec4f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717719"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="974ea-102">Интерфейс IValidator</span><span class="sxs-lookup"><span data-stu-id="974ea-102">IValidator Interface</span></span>
<span data-ttu-id="974ea-103">Предоставляет методы для проверки переносимого исполняемого (PE) образа и сообщение об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="974ea-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="974ea-104">Методы</span><span class="sxs-lookup"><span data-stu-id="974ea-104">Methods</span></span>  
  
|<span data-ttu-id="974ea-105">Метод</span><span class="sxs-lookup"><span data-stu-id="974ea-105">Method</span></span>|<span data-ttu-id="974ea-106">Описание</span><span class="sxs-lookup"><span data-stu-id="974ea-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="974ea-107">Validate</span><span class="sxs-lookup"><span data-stu-id="974ea-107">Validate</span></span>|<span data-ttu-id="974ea-108">Проверяет указанный промежуточного языка MSIL файл PE или Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="974ea-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="974ea-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="974ea-109">FormatEventInfo</span></span>|<span data-ttu-id="974ea-110">Получает сообщение об ошибке, соответствующее указанной ошибкой проверки.</span><span class="sxs-lookup"><span data-stu-id="974ea-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="974ea-111">Требования</span><span class="sxs-lookup"><span data-stu-id="974ea-111">Requirements</span></span>  
 <span data-ttu-id="974ea-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="974ea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="974ea-113">**Заголовок.** IValidator.idl в файле IValidator.h</span><span class="sxs-lookup"><span data-stu-id="974ea-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="974ea-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="974ea-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="974ea-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="974ea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="974ea-116">См. также</span><span class="sxs-lookup"><span data-stu-id="974ea-116">See also</span></span>
- [<span data-ttu-id="974ea-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="974ea-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="974ea-118">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="974ea-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
