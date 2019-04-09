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
ms.openlocfilehash: f40e6bfdbebdadc41da52564348c6070c18372c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194686"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="efff5-102">Метод IMetaDataImport::GetModuleFromScope</span><span class="sxs-lookup"><span data-stu-id="efff5-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="efff5-103">Получает маркер метаданных для модуля в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="efff5-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efff5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efff5-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efff5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="efff5-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="efff5-106">[out] Указатель на токен, представляющий модуль, указанный в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="efff5-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efff5-107">Требования</span><span class="sxs-lookup"><span data-stu-id="efff5-107">Requirements</span></span>  
 <span data-ttu-id="efff5-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efff5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efff5-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="efff5-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="efff5-110">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="efff5-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="efff5-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="efff5-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="efff5-112">См. также</span><span class="sxs-lookup"><span data-stu-id="efff5-112">See also</span></span>

- [<span data-ttu-id="efff5-113">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="efff5-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="efff5-114">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="efff5-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
