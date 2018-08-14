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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 053c94bc540b130510f155506b6fad32f032a475
ms.sourcegitcommit: a474397fd4de822f0d878d86d907e49763872b0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "33449550"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="07ffa-102">Метод IMetaDataValidate::ValidatorInit</span><span class="sxs-lookup"><span data-stu-id="07ffa-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="07ffa-103">Устанавливает флаг, который указывает тип модуля в текущей области метаданных, и регистрирует указанный метод обратного вызова для ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="07ffa-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07ffa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07ffa-104">Syntax</span></span>  
  
```  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07ffa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="07ffa-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="07ffa-106">[in] Значение [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) перечисления, указывающее тип модуля в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="07ffa-106">[in] A value of the [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="07ffa-107">[in] Указатель на [IUnknown](/cpp/atl/iunknown) экземпляр, который служит в качестве функцию обратного вызова для ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="07ffa-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07ffa-108">Требования</span><span class="sxs-lookup"><span data-stu-id="07ffa-108">Requirements</span></span>  
 <span data-ttu-id="07ffa-109">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07ffa-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07ffa-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="07ffa-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07ffa-111">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="07ffa-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="07ffa-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07ffa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ffa-113">См. также</span><span class="sxs-lookup"><span data-stu-id="07ffa-113">See Also</span></span>  
 [<span data-ttu-id="07ffa-114">Интерфейс IMetaDataValidate</span><span class="sxs-lookup"><span data-stu-id="07ffa-114">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
