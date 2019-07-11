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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e4be840760782789aa91e5519f60374aca2e3941
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775260"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="6e0a9-102">Метод IMetaDataAssemblyEmit::SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="6e0a9-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="6e0a9-103">Изменяет указанную структуру метаданных `ExportedType`.</span><span class="sxs-lookup"><span data-stu-id="6e0a9-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e0a9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e0a9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e0a9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e0a9-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="6e0a9-106">[in] Токен метаданных, указывающее `ExportedType` изменение структуры метаданных.</span><span class="sxs-lookup"><span data-stu-id="6e0a9-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="6e0a9-107">[in] Токен типа `File`, `AssemblyRef`, или `ExportedType`, указывающий реализации этого типа.</span><span class="sxs-lookup"><span data-stu-id="6e0a9-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="6e0a9-108">[in] `TypeDef` Токена, на которые ссылается файл кода.</span><span class="sxs-lookup"><span data-stu-id="6e0a9-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="6e0a9-109">[in] Побитовое сочетание значений, определяющих атрибуты типа.</span><span class="sxs-lookup"><span data-stu-id="6e0a9-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e0a9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="6e0a9-110">Remarks</span></span>  
 <span data-ttu-id="6e0a9-111">Чтобы создать `ExportedType` структура метаданных, используйте [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="6e0a9-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e0a9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6e0a9-112">Requirements</span></span>  
 <span data-ttu-id="6e0a9-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e0a9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e0a9-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6e0a9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e0a9-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6e0a9-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e0a9-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e0a9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e0a9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6e0a9-117">See also</span></span>

- [<span data-ttu-id="6e0a9-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="6e0a9-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
