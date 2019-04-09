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
ms.openlocfilehash: 5c09140488730179616d11932faa3542f704958a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123751"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="ee6eb-102">Метод IMetaDataAssemblyEmit::SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="ee6eb-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="ee6eb-103">Изменяет указанную структуру метаданных `ExportedType`.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee6eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee6eb-104">Syntax</span></span>  
  
```  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee6eb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ee6eb-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="ee6eb-106">[in] Токен метаданных, указывающее `ExportedType` изменение структуры метаданных.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="ee6eb-107">[in] Токен типа `File`, `AssemblyRef`, или `ExportedType`, указывающий реализации этого типа.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="ee6eb-108">[in] `TypeDef` Токена, на которые ссылается файл кода.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="ee6eb-109">[in] Побитовое сочетание значений, определяющих атрибуты типа.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee6eb-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ee6eb-110">Remarks</span></span>  
 <span data-ttu-id="ee6eb-111">Чтобы создать `ExportedType` структура метаданных, используйте [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="ee6eb-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee6eb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ee6eb-112">Requirements</span></span>  
 <span data-ttu-id="ee6eb-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee6eb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee6eb-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ee6eb-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee6eb-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ee6eb-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="ee6eb-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ee6eb-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ee6eb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ee6eb-117">See also</span></span>

- [<span data-ttu-id="ee6eb-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="ee6eb-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
