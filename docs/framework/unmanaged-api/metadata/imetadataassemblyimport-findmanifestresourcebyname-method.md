---
title: "Метод IMetaDataAssemblyImport::FindManifestResourceByName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.FindManifestResourceByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d6cc738c227157b45e242fb46a672d28d6ce778
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="bdeaf-102">Метод IMetaDataAssemblyImport::FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="bdeaf-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="bdeaf-103">Получает указатель на ресурс манифеста с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="bdeaf-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdeaf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdeaf-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="bdeaf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdeaf-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="bdeaf-106">[in] Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="bdeaf-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="bdeaf-107">[out] Массив, используемый для хранения `mdManifestResource` лексемы метаданных, каждый из которых представляет ресурс манифеста.</span><span class="sxs-lookup"><span data-stu-id="bdeaf-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdeaf-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="bdeaf-108">Remarks</span></span>  
 <span data-ttu-id="bdeaf-109">`FindManifestResourceByName` Метод использует стандартных правил, применяемых средой CLR для разрешения ссылок.</span><span class="sxs-lookup"><span data-stu-id="bdeaf-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdeaf-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bdeaf-110">Requirements</span></span>  
 <span data-ttu-id="bdeaf-111">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdeaf-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdeaf-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bdeaf-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bdeaf-113">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bdeaf-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bdeaf-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdeaf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdeaf-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bdeaf-115">See Also</span></span>  
 [<span data-ttu-id="bdeaf-116">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="bdeaf-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="bdeaf-117">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="bdeaf-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
