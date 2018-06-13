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
ms.openlocfilehash: c15c554e0ec135b33d671a83b5e27d0a2a89b731
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444260"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="71bda-102">Метод IMetaDataEmit::ApplyEditAndContinue</span><span class="sxs-lookup"><span data-stu-id="71bda-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="71bda-103">Обновляет текущую область сборки с изменениями, сделанными в указанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="71bda-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71bda-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71bda-104">Syntax</span></span>  
  
```  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71bda-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="71bda-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="71bda-106">[in] Указатель на <<!--zzxref:IUnknown --> `IUnknown`>, представляющий дельта метаданных из переносимого исполняемого (PE) файла.</span><span class="sxs-lookup"><span data-stu-id="71bda-106">[in] Pointer to an <<!--zzxref:IUnknown --> `IUnknown`> object that represents the delta metadata from the portable executable (PE) file.</span></span>  
  
 <span data-ttu-id="71bda-107">Разностные метаданные — это блок метаданных, содержащих изменения, внесенные в копию фактических метаданных модуля.</span><span class="sxs-lookup"><span data-stu-id="71bda-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71bda-108">Требования</span><span class="sxs-lookup"><span data-stu-id="71bda-108">Requirements</span></span>  
 <span data-ttu-id="71bda-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71bda-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71bda-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="71bda-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71bda-111">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71bda-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71bda-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71bda-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71bda-113">См. также</span><span class="sxs-lookup"><span data-stu-id="71bda-113">See Also</span></span>  
 [<span data-ttu-id="71bda-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="71bda-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="71bda-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="71bda-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
