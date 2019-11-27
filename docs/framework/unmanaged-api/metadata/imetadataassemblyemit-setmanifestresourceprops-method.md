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
ms.openlocfilehash: f6b5e12df60663b75e10b04eaa008a75d720d753
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434440"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="d7060-102">Метод IMetaDataAssemblyEmit::SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="d7060-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="d7060-103">Изменяет указанную структуру метаданных `ManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="d7060-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7060-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7060-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7060-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7060-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="d7060-106">окне Токен, указывающий структуру метаданных `ManifestResource`, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="d7060-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="d7060-107">окне Токен типа `File` или `AssemblyRef`, который сопоставляется с поставщиком ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d7060-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="d7060-108">окне Смещение в начале ресурса в файле.</span><span class="sxs-lookup"><span data-stu-id="d7060-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="d7060-109">окне Побитовое сочетание значений флагов, задающих атрибуты ресурса.</span><span class="sxs-lookup"><span data-stu-id="d7060-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7060-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7060-110">Remarks</span></span>  
 <span data-ttu-id="d7060-111">Чтобы создать `ManifestResource` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинеманифестресаурце](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d7060-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7060-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d7060-112">Requirements</span></span>  
 <span data-ttu-id="d7060-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7060-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7060-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="d7060-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7060-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d7060-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7060-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7060-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7060-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="d7060-117">See also</span></span>

- [<span data-ttu-id="d7060-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="d7060-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
