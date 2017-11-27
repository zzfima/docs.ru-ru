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
ms.openlocfilehash: 492f8a50c421df56d1b2f79d15d86ef3251b401e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="7e5d6-102">Метод IMetaDataAssemblyImport::FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="7e5d6-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="7e5d6-103">Получает указатель на ресурс манифеста с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="7e5d6-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e5d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e5d6-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e5d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e5d6-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="7e5d6-106">[in] Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="7e5d6-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="7e5d6-107">[out] Массив, используемый для хранения `mdManifestResource` лексемы метаданных, каждый из которых представляет ресурс манифеста.</span><span class="sxs-lookup"><span data-stu-id="7e5d6-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e5d6-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e5d6-108">Remarks</span></span>  
 <span data-ttu-id="7e5d6-109">`FindManifestResourceByName` Метод использует стандартных правил, применяемых средой CLR для разрешения ссылок.</span><span class="sxs-lookup"><span data-stu-id="7e5d6-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e5d6-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7e5d6-110">Requirements</span></span>  
 <span data-ttu-id="7e5d6-111">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e5d6-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e5d6-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7e5d6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e5d6-113">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e5d6-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7e5d6-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e5d6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e5d6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7e5d6-115">See Also</span></span>  
 [<span data-ttu-id="7e5d6-116">Imetadataassemblyimport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="7e5d6-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="7e5d6-117">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="7e5d6-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
