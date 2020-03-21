---
title: Метод IMetaDataAssemblyEmit::SetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
ms.openlocfilehash: dd1d6f1da6e49837eebd9356500f403c199b011b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177854"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="766ea-102">Метод IMetaDataAssemblyEmit::SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="766ea-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="766ea-103">Изменяет указанную структуру метаданных `ExportedType`.</span><span class="sxs-lookup"><span data-stu-id="766ea-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="766ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="766ea-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="766ea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="766ea-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="766ea-106">(в) Токен метаданных, который определяет `ExportedType` структуру метаданных для изменения.</span><span class="sxs-lookup"><span data-stu-id="766ea-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="766ea-107">(в) Токен, типа, `File` `AssemblyRef`или `ExportedType`, который определяет, как этот тип реализуется.</span><span class="sxs-lookup"><span data-stu-id="766ea-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="766ea-108">(в) Токен, `TypeDef` упомянутый в файле кода.</span><span class="sxs-lookup"><span data-stu-id="766ea-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="766ea-109">(в) Битовая комбинация значений, определяющих атрибуты типа.</span><span class="sxs-lookup"><span data-stu-id="766ea-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="766ea-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="766ea-110">Remarks</span></span>  
 <span data-ttu-id="766ea-111">Для создания `ExportedType` структуры метаданных используйте метод [IMetaDataAssemblyEmit::DefineExportedType.](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)</span><span class="sxs-lookup"><span data-stu-id="766ea-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="766ea-112">Требования</span><span class="sxs-lookup"><span data-stu-id="766ea-112">Requirements</span></span>  
 <span data-ttu-id="766ea-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="766ea-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="766ea-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="766ea-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="766ea-115">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="766ea-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="766ea-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="766ea-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="766ea-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="766ea-117">See also</span></span>

- [<span data-ttu-id="766ea-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="766ea-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
