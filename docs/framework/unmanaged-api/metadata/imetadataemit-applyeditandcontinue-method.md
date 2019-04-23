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
ms.openlocfilehash: c18c72ecbaf2e0d3153ad7f00caf73421e35fa0a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225317"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="22a06-102">Метод IMetaDataEmit::ApplyEditAndContinue</span><span class="sxs-lookup"><span data-stu-id="22a06-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="22a06-103">Обновляет текущую область сборки с изменениями, сделанными в указанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="22a06-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a06-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22a06-104">Syntax</span></span>  
  
```  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22a06-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="22a06-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="22a06-106">\[в\] указатель на [IUnknown](/cpp/atl/iunknown) объект, представляющий дельта метаданных из переносимого исполняемого (PE) файла.</span><span class="sxs-lookup"><span data-stu-id="22a06-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="22a06-107">Разностные метаданные — этот блок метаданных, который включает в себя изменения, внесенные в копию модуля фактические метаданные.</span><span class="sxs-lookup"><span data-stu-id="22a06-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22a06-108">Требования</span><span class="sxs-lookup"><span data-stu-id="22a06-108">Requirements</span></span>  
 <span data-ttu-id="22a06-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22a06-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22a06-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="22a06-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22a06-111">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22a06-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22a06-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22a06-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22a06-113">См. также</span><span class="sxs-lookup"><span data-stu-id="22a06-113">See also</span></span>

- [<span data-ttu-id="22a06-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="22a06-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="22a06-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="22a06-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
