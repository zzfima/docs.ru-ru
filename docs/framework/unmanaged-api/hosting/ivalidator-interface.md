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
ms.openlocfilehash: 1a732e59d539c330f91e8665e81dc4771b40e2d0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123288"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="04dee-102">Интерфейс IValidator</span><span class="sxs-lookup"><span data-stu-id="04dee-102">IValidator Interface</span></span>
<span data-ttu-id="04dee-103">Предоставляет методы для проверки переносимых исполняемых (PE) образов и создания отчетов об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="04dee-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04dee-104">Методы</span><span class="sxs-lookup"><span data-stu-id="04dee-104">Methods</span></span>  
  
|<span data-ttu-id="04dee-105">Метод</span><span class="sxs-lookup"><span data-stu-id="04dee-105">Method</span></span>|<span data-ttu-id="04dee-106">Описание</span><span class="sxs-lookup"><span data-stu-id="04dee-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="04dee-107">Validate</span><span class="sxs-lookup"><span data-stu-id="04dee-107">Validate</span></span>|<span data-ttu-id="04dee-108">Проверяет указанный PE-файл или промежуточный язык MSIL.</span><span class="sxs-lookup"><span data-stu-id="04dee-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="04dee-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="04dee-109">FormatEventInfo</span></span>|<span data-ttu-id="04dee-110">Возвращает сообщение об ошибке, соответствующее указанной ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="04dee-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04dee-111">Требования</span><span class="sxs-lookup"><span data-stu-id="04dee-111">Requirements</span></span>  
 <span data-ttu-id="04dee-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04dee-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04dee-113">**Заголовок:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="04dee-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="04dee-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="04dee-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04dee-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04dee-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04dee-116">См. также</span><span class="sxs-lookup"><span data-stu-id="04dee-116">See also</span></span>

- [<span data-ttu-id="04dee-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="04dee-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="04dee-118">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="04dee-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
