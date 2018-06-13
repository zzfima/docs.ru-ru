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
ms.openlocfilehash: 048c7234fcb2592ea0dade135a32341a6e0f404f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444923"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="5ff1a-102">Метод IMetaDataAssemblyImport::FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="5ff1a-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="5ff1a-103">Получает указатель на экспортируемый тип по его имени и включающий тип.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff1a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ff1a-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ff1a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ff1a-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="5ff1a-106">[in] Имя экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="5ff1a-107">[in] Токен метаданных для экспортируемого типа включающего класса.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="5ff1a-108">Это значение равно `mdExportedTypeNil` при экспорте запрошенный тип не является вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="5ff1a-109">[out] Указатель на `mdExportedType` токен, представляющий экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ff1a-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ff1a-110">Remarks</span></span>  
 <span data-ttu-id="5ff1a-111">`FindExportedTypeByName` Метод использует стандартных правил, применяемых средой CLR для разрешения ссылок.</span><span class="sxs-lookup"><span data-stu-id="5ff1a-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ff1a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5ff1a-112">Requirements</span></span>  
 <span data-ttu-id="5ff1a-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ff1a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ff1a-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5ff1a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ff1a-115">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ff1a-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ff1a-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ff1a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff1a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5ff1a-117">See Also</span></span>  
 [<span data-ttu-id="5ff1a-118">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="5ff1a-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="5ff1a-119">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="5ff1a-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
