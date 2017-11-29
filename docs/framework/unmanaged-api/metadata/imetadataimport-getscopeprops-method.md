---
title: "Метод IMetaDataImport::GetScopeProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetScopeProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5b0936a9f47e2d0fa52816b78a7eecf3d244d594
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="4e9b9-102">Метод IMetaDataImport::GetScopeProps</span><span class="sxs-lookup"><span data-stu-id="4e9b9-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="4e9b9-103">Возвращает имя и при необходимости идентификатор версии сборки или модуля в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="4e9b9-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e9b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e9b9-104">Syntax</span></span>  
  
```  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e9b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4e9b9-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="4e9b9-106">[out] Буфер для имени сборки или модуля.</span><span class="sxs-lookup"><span data-stu-id="4e9b9-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4e9b9-107">[in] Размер в расширенных символах с `szName`.</span><span class="sxs-lookup"><span data-stu-id="4e9b9-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="4e9b9-108">[out] Число расширенных символов, возвращаемых в `szName`.</span><span class="sxs-lookup"><span data-stu-id="4e9b9-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="4e9b9-109">[out, optional] Указатель на идентификатор GUID, который уникально идентифицирует версию сборки или модуля.</span><span class="sxs-lookup"><span data-stu-id="4e9b9-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e9b9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e9b9-110">Remarks</span></span>  
 <span data-ttu-id="4e9b9-111">[IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) метод используется для установки этих свойств.</span><span class="sxs-lookup"><span data-stu-id="4e9b9-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e9b9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4e9b9-112">Requirements</span></span>  
 <span data-ttu-id="4e9b9-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e9b9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e9b9-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4e9b9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e9b9-115">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e9b9-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e9b9-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e9b9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e9b9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4e9b9-117">See Also</span></span>  
 [<span data-ttu-id="4e9b9-118">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4e9b9-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="4e9b9-119">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4e9b9-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
