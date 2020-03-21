---
title: Метод IMetaDataAssemblyEmit::DefineExportedType
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
ms.openlocfilehash: 388f227377ddf73fe1297e1c777bb1c0607c13d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177881"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="630f3-102">Метод IMetaDataAssemblyEmit::DefineExportedType</span><span class="sxs-lookup"><span data-stu-id="630f3-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="630f3-103">Создает структуру `ExportedType`, содержащую метаданные для указанного экспортированного типа, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="630f3-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="630f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="630f3-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="630f3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="630f3-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="630f3-106">(в) Название типа, которое будет экспортироваться.</span><span class="sxs-lookup"><span data-stu-id="630f3-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="630f3-107">Для версии 1.1 общего времени выполнения языка имя экспортируемого типа должно `TypeDef` точно соответствовать названию, приведенному в типе.</span><span class="sxs-lookup"><span data-stu-id="630f3-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="630f3-108">(в) Токен с указанием места реализации экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="630f3-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="630f3-109">Действительные значения и связанные с ними значения:</span><span class="sxs-lookup"><span data-stu-id="630f3-109">The valid values and their associated meanings are:</span></span>  
  
- <span data-ttu-id="630f3-110">`mdFile`Тип реализован в другом файле в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="630f3-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
- <span data-ttu-id="630f3-111">`mdAssemblyRef`Тип реализован в другой сборке.</span><span class="sxs-lookup"><span data-stu-id="630f3-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
- <span data-ttu-id="630f3-112">`mdExportedTYpe`Тип вложен в какой-либо другой тип.</span><span class="sxs-lookup"><span data-stu-id="630f3-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
- <span data-ttu-id="630f3-113">`mdFileNil`Тип находится в том же файле, что и манифест, и не является вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="630f3-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="630f3-114">(в) Токен к метаданным, который определяет тип, который будет экспортироваться.</span><span class="sxs-lookup"><span data-stu-id="630f3-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="630f3-115">Это значение вводится `TypeDef` в таблицу в файле, который реализует тип и актуален только в том случае, если этот файл находится в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="630f3-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="630f3-116">(в) Битовая комбинация значений [corTypeAttr,](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) определяющих параметры свойств для экспортируемого типа.</span><span class="sxs-lookup"><span data-stu-id="630f3-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="630f3-117">(ваут) Указатель на токен возвращенных метаданных, указывающий на экспортированный тип.</span><span class="sxs-lookup"><span data-stu-id="630f3-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="630f3-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="630f3-118">Remarks</span></span>  
 <span data-ttu-id="630f3-119">Структура `ExportedType` метаданных должна быть определена для каждого типа, который подвергается этой сборке и реализован в модуле, кроме того, который содержит манифест.</span><span class="sxs-lookup"><span data-stu-id="630f3-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="630f3-120">Требования</span><span class="sxs-lookup"><span data-stu-id="630f3-120">Requirements</span></span>  
 <span data-ttu-id="630f3-121">**Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="630f3-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="630f3-122">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="630f3-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="630f3-123">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="630f3-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="630f3-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="630f3-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="630f3-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="630f3-125">See also</span></span>

- [<span data-ttu-id="630f3-126">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="630f3-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
