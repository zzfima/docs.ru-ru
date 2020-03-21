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
ms.openlocfilehash: ae9097725aecd21e910e49a78d81951df39e9b2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177777"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="c6227-102">Метод IMetaDataAssemblyImport::FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="c6227-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="c6227-103">Получает указатель на ресурс манифеста с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="c6227-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6227-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6227-104">Syntax</span></span>  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,
    [out] mdManifestResource     *ptkManifestResource  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="c6227-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6227-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="c6227-106">[in] Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="c6227-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="c6227-107">(ваут) Массив, используемый `mdManifestResource` для хранения токенов метаданных, каждый из которых представляет собой манифест ресурс.</span><span class="sxs-lookup"><span data-stu-id="c6227-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6227-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c6227-108">Remarks</span></span>  
 <span data-ttu-id="c6227-109">Метод `FindManifestResourceByName` использует стандартные правила, используемые общим языком времени выполнения для решения ссылок.</span><span class="sxs-lookup"><span data-stu-id="c6227-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6227-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c6227-110">Requirements</span></span>  
 <span data-ttu-id="c6227-111">**Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6227-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6227-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c6227-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6227-113">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6227-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6227-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6227-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6227-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c6227-115">See also</span></span>

- [<span data-ttu-id="c6227-116">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="c6227-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="c6227-117">Как Время выполнения находит сборки</span><span class="sxs-lookup"><span data-stu-id="c6227-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
