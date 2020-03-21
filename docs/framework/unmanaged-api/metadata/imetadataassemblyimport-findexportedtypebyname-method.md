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
ms.openlocfilehash: edfe5de9c9d7ef9607a2eea5146194bbd4393a92
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175997"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="7365d-102">Метод IMetaDataAssemblyImport::FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="7365d-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="7365d-103">Получает указатель на экспортированный тип, учитывая его имя и прилагающий тип.</span><span class="sxs-lookup"><span data-stu-id="7365d-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7365d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7365d-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7365d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7365d-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="7365d-106">(в) Название экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="7365d-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="7365d-107">(в) Токен метаданных для прилагаемого класса экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="7365d-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="7365d-108">Это значение, `mdExportedTypeNil` если запрашиваемый экспортированный тип не является вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="7365d-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="7365d-109">(ваут) Указатель на `mdExportedType` токен, представляющий экспортированный тип.</span><span class="sxs-lookup"><span data-stu-id="7365d-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7365d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="7365d-110">Remarks</span></span>  
 <span data-ttu-id="7365d-111">Метод `FindExportedTypeByName` использует стандартные правила, используемые общим языком времени выполнения для решения ссылок.</span><span class="sxs-lookup"><span data-stu-id="7365d-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7365d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7365d-112">Requirements</span></span>  
 <span data-ttu-id="7365d-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7365d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7365d-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7365d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7365d-115">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7365d-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7365d-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7365d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7365d-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7365d-117">See also</span></span>

- [<span data-ttu-id="7365d-118">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="7365d-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="7365d-119">Как Время выполнения находит сборки</span><span class="sxs-lookup"><span data-stu-id="7365d-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
