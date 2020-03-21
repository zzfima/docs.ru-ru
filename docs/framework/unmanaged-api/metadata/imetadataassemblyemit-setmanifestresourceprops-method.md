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
ms.openlocfilehash: 9370b27fd385b0223b354365d64aa57048f4ec69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177841"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="b552f-102">Метод IMetaDataAssemblyEmit::SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="b552f-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="b552f-103">Изменяет указанную структуру метаданных `ManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="b552f-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b552f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b552f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b552f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b552f-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="b552f-106">(в) Токен, описавший `ManifestResource` структуру метаданных для изменения.</span><span class="sxs-lookup"><span data-stu-id="b552f-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="b552f-107">(в) Токен, типа `File` или `AssemblyRef`, что карты для поставщика ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b552f-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="b552f-108">(в) Смещение до начала ресурса в файле.</span><span class="sxs-lookup"><span data-stu-id="b552f-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="b552f-109">(в) Битовая комбинация значений флага, определяющих атрибуты ресурса.</span><span class="sxs-lookup"><span data-stu-id="b552f-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b552f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b552f-110">Remarks</span></span>  
 <span data-ttu-id="b552f-111">Для создания `ManifestResource` структуры метаданных используйте метод [IMetaDataAssemblyEmit::DefineManifestResource.](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)</span><span class="sxs-lookup"><span data-stu-id="b552f-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b552f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b552f-112">Requirements</span></span>  
 <span data-ttu-id="b552f-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b552f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b552f-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b552f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b552f-115">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b552f-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b552f-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b552f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b552f-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b552f-117">See also</span></span>

- [<span data-ttu-id="b552f-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="b552f-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
