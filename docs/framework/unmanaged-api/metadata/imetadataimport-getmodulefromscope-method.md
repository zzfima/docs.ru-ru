---
title: Метод IMetaDataImport::GetModuleFromScope
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05ce699669095e9c0b45882b18a01ec326640038
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779006"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="e67f8-102">Метод IMetaDataImport::GetModuleFromScope</span><span class="sxs-lookup"><span data-stu-id="e67f8-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="e67f8-103">Получает маркер метаданных для модуля в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="e67f8-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e67f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e67f8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e67f8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e67f8-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="e67f8-106">[out] Указатель на токен, представляющий модуль, указанный в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="e67f8-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e67f8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e67f8-107">Requirements</span></span>  
 <span data-ttu-id="e67f8-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e67f8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e67f8-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e67f8-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e67f8-110">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e67f8-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e67f8-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e67f8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e67f8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e67f8-112">See also</span></span>

- [<span data-ttu-id="e67f8-113">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e67f8-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e67f8-114">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e67f8-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
