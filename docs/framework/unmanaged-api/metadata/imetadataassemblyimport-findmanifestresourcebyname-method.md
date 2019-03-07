---
title: Метод IMetaDataAssemblyImport::FindManifestResourceByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d736a93e7ba6451f1d4755a86749565b9ea071b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491522"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="80ac6-102">Метод IMetaDataAssemblyImport::FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="80ac6-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="80ac6-103">Возвращает указатель на ресурс манифеста с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="80ac6-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80ac6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80ac6-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="80ac6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="80ac6-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="80ac6-106">[in] Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="80ac6-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="80ac6-107">[out] Массив, используемый для хранения `mdManifestResource` маркеров метаданных, каждый из которых представляет ресурса манифеста.</span><span class="sxs-lookup"><span data-stu-id="80ac6-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80ac6-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="80ac6-108">Remarks</span></span>  
 <span data-ttu-id="80ac6-109">`FindManifestResourceByName` Метод использует стандартные правила, чтобы позволить среда CLR для разрешения ссылок на.</span><span class="sxs-lookup"><span data-stu-id="80ac6-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80ac6-110">Требования</span><span class="sxs-lookup"><span data-stu-id="80ac6-110">Requirements</span></span>  
 <span data-ttu-id="80ac6-111">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80ac6-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80ac6-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="80ac6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80ac6-113">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80ac6-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80ac6-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80ac6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ac6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="80ac6-115">See also</span></span>
- [<span data-ttu-id="80ac6-116">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="80ac6-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="80ac6-117">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="80ac6-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
