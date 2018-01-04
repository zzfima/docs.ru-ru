---
title: "Метод IMetaDataAssemblyImport::FindExportedTypeByName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.FindExportedTypeByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 010e6c29541e4b55353db4359c018935c5e1ef2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="41a65-102">Метод IMetaDataAssemblyImport::FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="41a65-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="41a65-103">Получает указатель на экспортируемый тип по его имени и включающий тип.</span><span class="sxs-lookup"><span data-stu-id="41a65-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41a65-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41a65-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41a65-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="41a65-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="41a65-106">[in] Имя экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="41a65-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="41a65-107">[in] Токен метаданных для экспортируемого типа включающего класса.</span><span class="sxs-lookup"><span data-stu-id="41a65-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="41a65-108">Это значение равно `mdExportedTypeNil` при экспорте запрошенный тип не является вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="41a65-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="41a65-109">[out] Указатель на `mdExportedType` токен, представляющий экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="41a65-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41a65-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="41a65-110">Remarks</span></span>  
 <span data-ttu-id="41a65-111">`FindExportedTypeByName` Метод использует стандартных правил, применяемых средой CLR для разрешения ссылок.</span><span class="sxs-lookup"><span data-stu-id="41a65-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41a65-112">Требования</span><span class="sxs-lookup"><span data-stu-id="41a65-112">Requirements</span></span>  
 <span data-ttu-id="41a65-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41a65-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41a65-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="41a65-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41a65-115">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="41a65-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41a65-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41a65-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a65-117">См. также</span><span class="sxs-lookup"><span data-stu-id="41a65-117">See Also</span></span>  
 [<span data-ttu-id="41a65-118">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="41a65-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="41a65-119">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="41a65-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
