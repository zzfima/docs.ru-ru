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
ms.openlocfilehash: 8643a4d207fb570195caa00a1ac659c78c2ff2b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445071"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="cb3fc-102">Метод IMetaDataAssemblyEmit::SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="cb3fc-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="cb3fc-103">Изменяет указанную структуру метаданных `ExportedType`.</span><span class="sxs-lookup"><span data-stu-id="cb3fc-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb3fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb3fc-104">Syntax</span></span>  
  
```  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb3fc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cb3fc-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="cb3fc-106">[in] Токен метаданных, указывает `ExportedType` изменение структуры метаданных.</span><span class="sxs-lookup"><span data-stu-id="cb3fc-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="cb3fc-107">[in] Маркер типа `File`, `AssemblyRef`, или `ExportedType`, указывающий реализации этого типа.</span><span class="sxs-lookup"><span data-stu-id="cb3fc-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="cb3fc-108">[in] `TypeDef` Маркер, указанный в файле кода.</span><span class="sxs-lookup"><span data-stu-id="cb3fc-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="cb3fc-109">[in] Побитовое сочетание значений, которые определяют атрибуты типа.</span><span class="sxs-lookup"><span data-stu-id="cb3fc-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb3fc-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb3fc-110">Remarks</span></span>  
 <span data-ttu-id="cb3fc-111">Для создания `ExportedType` структуру метаданных, используйте [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="cb3fc-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb3fc-112">Требования</span><span class="sxs-lookup"><span data-stu-id="cb3fc-112">Requirements</span></span>  
 <span data-ttu-id="cb3fc-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb3fc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb3fc-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cb3fc-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb3fc-115">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb3fc-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cb3fc-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb3fc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb3fc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="cb3fc-117">See Also</span></span>  
 [<span data-ttu-id="cb3fc-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="cb3fc-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
