---
title: Метод IMetaDataAssemblyEmit::SetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6fbc3f41e95730e93bd907762dd8cd4205037c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187308"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="1a5c5-102">Метод IMetaDataAssemblyEmit::SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="1a5c5-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="1a5c5-103">Изменяет указанную структуру метаданных `ManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="1a5c5-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a5c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a5c5-104">Syntax</span></span>  
  
```  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a5c5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1a5c5-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="1a5c5-106">[in] Токен, который указывает `ManifestResource` изменение структуры метаданных.</span><span class="sxs-lookup"><span data-stu-id="1a5c5-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="1a5c5-107">[in] Токен типа `File` или `AssemblyRef`, который сопоставляет к поставщику ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1a5c5-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="1a5c5-108">[in] Смещение в начало ресурса в файле.</span><span class="sxs-lookup"><span data-stu-id="1a5c5-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="1a5c5-109">[in] Побитовое сочетание значения флагов, определяющих атрибуты ресурса.</span><span class="sxs-lookup"><span data-stu-id="1a5c5-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a5c5-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a5c5-110">Remarks</span></span>  
 <span data-ttu-id="1a5c5-111">Чтобы создать `ManifestResource` структура метаданных, используйте [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="1a5c5-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a5c5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1a5c5-112">Requirements</span></span>  
 <span data-ttu-id="1a5c5-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a5c5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a5c5-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1a5c5-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1a5c5-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a5c5-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="1a5c5-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1a5c5-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1a5c5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1a5c5-117">See also</span></span>

- [<span data-ttu-id="1a5c5-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="1a5c5-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
