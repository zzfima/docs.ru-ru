---
title: Метод IMetaDataEmit::ApplyEditAndContinue
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.ApplyEditAndContinue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::ApplyEditAndContinue
helpviewer_keywords:
- ApplyEditAndContinue method [.NET Framework metadata]
- IMetaDataEmit::ApplyEditAndContinue method [.NET Framework metadata]
ms.assetid: 35991289-f389-495d-8caa-a6384fb1d557
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: faa9bc412e67e0e49ee969bd8b246a424fe628a0
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45589093"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="cf8aa-102">Метод IMetaDataEmit::ApplyEditAndContinue</span><span class="sxs-lookup"><span data-stu-id="cf8aa-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="cf8aa-103">Обновляет текущую область сборки с изменениями, сделанными в указанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="cf8aa-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf8aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf8aa-104">Syntax</span></span>  
  
```  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf8aa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf8aa-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="cf8aa-106">\[в\] указатель на [IUnknown](/cpp/atl/iunknown) объект, представляющий дельта метаданных из переносимого исполняемого (PE) файла.</span><span class="sxs-lookup"><span data-stu-id="cf8aa-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="cf8aa-107">Разностные метаданные — этот блок метаданных, который включает в себя изменения, внесенные в копию модуля фактические метаданные.</span><span class="sxs-lookup"><span data-stu-id="cf8aa-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf8aa-108">Требования</span><span class="sxs-lookup"><span data-stu-id="cf8aa-108">Requirements</span></span>  
 <span data-ttu-id="cf8aa-109">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf8aa-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf8aa-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cf8aa-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf8aa-111">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cf8aa-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf8aa-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf8aa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf8aa-113">См. также</span><span class="sxs-lookup"><span data-stu-id="cf8aa-113">See Also</span></span>  
 [<span data-ttu-id="cf8aa-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="cf8aa-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="cf8aa-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="cf8aa-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
