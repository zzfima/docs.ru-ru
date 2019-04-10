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
ms.openlocfilehash: 17568a46c8e946989af0e401366d7eaa885886da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220972"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="72c47-102">Метод IMetaDataImport::GetScopeProps</span><span class="sxs-lookup"><span data-stu-id="72c47-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="72c47-103">Возвращает имя и при необходимости идентификатор версии сборки или модуля в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="72c47-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72c47-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72c47-104">Syntax</span></span>  
  
```  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72c47-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="72c47-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="72c47-106">[out] Буфер для имени сборки или модуля.</span><span class="sxs-lookup"><span data-stu-id="72c47-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="72c47-107">[in] Размер в расширенных символах `szName`.</span><span class="sxs-lookup"><span data-stu-id="72c47-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="72c47-108">[out] Число расширенных символов, возвращаемых в `szName`.</span><span class="sxs-lookup"><span data-stu-id="72c47-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="72c47-109">[out, optional] Указатель на GUID, который уникально идентифицирует версию сборки или модуля.</span><span class="sxs-lookup"><span data-stu-id="72c47-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72c47-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="72c47-110">Remarks</span></span>  
 <span data-ttu-id="72c47-111">[IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) метод используется для установки этих свойств.</span><span class="sxs-lookup"><span data-stu-id="72c47-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72c47-112">Требования</span><span class="sxs-lookup"><span data-stu-id="72c47-112">Requirements</span></span>  
 <span data-ttu-id="72c47-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72c47-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72c47-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="72c47-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72c47-115">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72c47-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="72c47-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="72c47-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="72c47-117">См. также</span><span class="sxs-lookup"><span data-stu-id="72c47-117">See also</span></span>

- [<span data-ttu-id="72c47-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="72c47-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="72c47-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="72c47-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
