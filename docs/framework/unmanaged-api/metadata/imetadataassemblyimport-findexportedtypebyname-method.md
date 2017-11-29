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
ms.openlocfilehash: b7ef0e09cb5a44e612e545fc4ee7278c2d128174
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="de9e7-102">Метод IMetaDataAssemblyImport::FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="de9e7-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="de9e7-103">Получает указатель на экспортируемый тип по его имени и включающий тип.</span><span class="sxs-lookup"><span data-stu-id="de9e7-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de9e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de9e7-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de9e7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="de9e7-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="de9e7-106">[in] Имя экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="de9e7-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="de9e7-107">[in] Токен метаданных для экспортируемого типа включающего класса.</span><span class="sxs-lookup"><span data-stu-id="de9e7-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="de9e7-108">Это значение равно `mdExportedTypeNil` при экспорте запрошенный тип не является вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="de9e7-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="de9e7-109">[out] Указатель на `mdExportedType` токен, представляющий экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="de9e7-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de9e7-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="de9e7-110">Remarks</span></span>  
 <span data-ttu-id="de9e7-111">`FindExportedTypeByName` Метод использует стандартных правил, применяемых средой CLR для разрешения ссылок.</span><span class="sxs-lookup"><span data-stu-id="de9e7-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de9e7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="de9e7-112">Requirements</span></span>  
 <span data-ttu-id="de9e7-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de9e7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de9e7-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="de9e7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de9e7-115">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="de9e7-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de9e7-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de9e7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de9e7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="de9e7-117">See Also</span></span>  
 [<span data-ttu-id="de9e7-118">Imetadataassemblyimport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="de9e7-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="de9e7-119">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="de9e7-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
