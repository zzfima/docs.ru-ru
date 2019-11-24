---
title: Метод IMetaDataValidate::ValidatorInit
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
ms.openlocfilehash: 165a57d8029fe03b9de3754fcf7c4db757292cec
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443602"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="8a423-102">Метод IMetaDataValidate::ValidatorInit</span><span class="sxs-lookup"><span data-stu-id="8a423-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="8a423-103">Устанавливает флаг, который указывает тип модуля в текущей области метаданных, и регистрирует указанный метод обратного вызова для ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="8a423-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a423-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a423-104">Syntax</span></span>  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a423-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a423-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="8a423-106">[in] A value of the [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="8a423-106">[in] A value of the [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="8a423-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span><span class="sxs-lookup"><span data-stu-id="8a423-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a423-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8a423-108">Requirements</span></span>  
 <span data-ttu-id="8a423-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a423-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a423-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8a423-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a423-111">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a423-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a423-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a423-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a423-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8a423-113">See also</span></span>

- [<span data-ttu-id="8a423-114">Интерфейс IMetaDataValidate</span><span class="sxs-lookup"><span data-stu-id="8a423-114">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
