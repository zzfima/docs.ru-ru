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
ms.openlocfilehash: e5fff28e1c2c0d31285c9621c184a44355813a03
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479692"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="f6689-102">Метод IMetaDataAssemblyEmit::SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="f6689-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="f6689-103">Изменяет указанную структуру метаданных `ExportedType`.</span><span class="sxs-lookup"><span data-stu-id="f6689-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6689-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6689-104">Syntax</span></span>  
  
```  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6689-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6689-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="f6689-106">[in] Токен метаданных, указывающее `ExportedType` изменение структуры метаданных.</span><span class="sxs-lookup"><span data-stu-id="f6689-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="f6689-107">[in] Токен типа `File`, `AssemblyRef`, или `ExportedType`, указывающий реализации этого типа.</span><span class="sxs-lookup"><span data-stu-id="f6689-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="f6689-108">[in] `TypeDef` Токена, на которые ссылается файл кода.</span><span class="sxs-lookup"><span data-stu-id="f6689-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="f6689-109">[in] Побитовое сочетание значений, определяющих атрибуты типа.</span><span class="sxs-lookup"><span data-stu-id="f6689-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6689-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6689-110">Remarks</span></span>  
 <span data-ttu-id="f6689-111">Чтобы создать `ExportedType` структура метаданных, используйте [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f6689-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6689-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f6689-112">Requirements</span></span>  
 <span data-ttu-id="f6689-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6689-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6689-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f6689-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6689-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6689-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6689-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6689-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6689-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f6689-117">See also</span></span>
- [<span data-ttu-id="f6689-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="f6689-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
