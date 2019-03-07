---
title: Метод IMetaDataImport::GetScopeProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e5d998bd85f1cc872acde74fdf954299a279c40
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466275"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="e19c6-102">Метод IMetaDataImport::GetScopeProps</span><span class="sxs-lookup"><span data-stu-id="e19c6-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="e19c6-103">Возвращает имя и при необходимости идентификатор версии сборки или модуля в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="e19c6-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e19c6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e19c6-104">Syntax</span></span>  
  
```  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e19c6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e19c6-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="e19c6-106">[out] Буфер для имени сборки или модуля.</span><span class="sxs-lookup"><span data-stu-id="e19c6-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="e19c6-107">[in] Размер в расширенных символах `szName`.</span><span class="sxs-lookup"><span data-stu-id="e19c6-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="e19c6-108">[out] Число расширенных символов, возвращаемых в `szName`.</span><span class="sxs-lookup"><span data-stu-id="e19c6-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="e19c6-109">[out, optional] Указатель на GUID, который уникально идентифицирует версию сборки или модуля.</span><span class="sxs-lookup"><span data-stu-id="e19c6-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e19c6-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="e19c6-110">Remarks</span></span>  
 <span data-ttu-id="e19c6-111">[IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) метод используется для установки этих свойств.</span><span class="sxs-lookup"><span data-stu-id="e19c6-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e19c6-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e19c6-112">Requirements</span></span>  
 <span data-ttu-id="e19c6-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e19c6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e19c6-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e19c6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e19c6-115">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e19c6-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e19c6-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e19c6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e19c6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e19c6-117">See also</span></span>
- [<span data-ttu-id="e19c6-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e19c6-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e19c6-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e19c6-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
