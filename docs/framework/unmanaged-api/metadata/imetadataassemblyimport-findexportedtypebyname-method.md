---
title: Метод IMetaDataAssemblyImport::FindExportedTypeByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8a70c041bc17f58a5e17877dd2e1f2aa2944e689
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777932"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="ea8a8-102">Метод IMetaDataAssemblyImport::FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="ea8a8-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="ea8a8-103">Получает указатель на экспортируемый тип по его имени и включающий тип.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea8a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea8a8-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea8a8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ea8a8-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="ea8a8-106">[in] Имя экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="ea8a8-107">[in] Маркер метаданных для экспортируемого типа включающего класса.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="ea8a8-108">Это значение равно `mdExportedTypeNil` при экспорте в запрошенный тип не является вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="ea8a8-109">[out] Указатель на `mdExportedType` токен, представляющий экспортированный тип.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea8a8-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ea8a8-110">Remarks</span></span>  
 <span data-ttu-id="ea8a8-111">`FindExportedTypeByName` Метод использует стандартные правила, чтобы позволить среда CLR для разрешения ссылок на.</span><span class="sxs-lookup"><span data-stu-id="ea8a8-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea8a8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ea8a8-112">Requirements</span></span>  
 <span data-ttu-id="ea8a8-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea8a8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea8a8-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ea8a8-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea8a8-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea8a8-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea8a8-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea8a8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8a8-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ea8a8-117">See also</span></span>

- [<span data-ttu-id="ea8a8-118">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="ea8a8-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="ea8a8-119">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="ea8a8-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
