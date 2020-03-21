---
title: Метод IMetaDataAssemblyEmit::DefineManifestResource
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
ms.openlocfilehash: 5aa5d78faa8ca9261594e2a649b11088e1d78ee7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177860"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="36ccf-102">Метод IMetaDataAssemblyEmit::DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="36ccf-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="36ccf-103">Создает структуру `ManifestResource`, содержащую метаданные для указанного ресурса манифеста, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="36ccf-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36ccf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36ccf-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36ccf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="36ccf-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="36ccf-106">[in] Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="36ccf-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="36ccf-107">(в) Токен метаданных типа `mdtFile` `mdtAssemblyRef` или карты поставщика ресурсов.</span><span class="sxs-lookup"><span data-stu-id="36ccf-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="36ccf-108">Значение NULL указывает на то, что файл, в который встроены метаданные, является поставщиком ресурсов.</span><span class="sxs-lookup"><span data-stu-id="36ccf-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="36ccf-109">(в) Смещение до начала ресурса в файле.</span><span class="sxs-lookup"><span data-stu-id="36ccf-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="36ccf-110">Для ресурсов в автономных файлах этот вопрос всегда будет равен нулю.</span><span class="sxs-lookup"><span data-stu-id="36ccf-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="36ccf-111">Если ресурс встроен в файл PE (портативный исполняемый) файл, это смещение ресурса BLOB, которое начинается в месте, указанном в файле заголовка cor.h.</span><span class="sxs-lookup"><span data-stu-id="36ccf-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="36ccf-112">(в) Битовая комбинация значений флага, определяющих параметры свойств для определения ресурса.</span><span class="sxs-lookup"><span data-stu-id="36ccf-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="36ccf-113">(ваут) Указатель на токен возвращенных метаданных.</span><span class="sxs-lookup"><span data-stu-id="36ccf-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36ccf-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="36ccf-114">Remarks</span></span>  
 <span data-ttu-id="36ccf-115">Для `ManifestResource` каждого ресурса, реализованного в файлах сборки, должна быть определена одна структура метаданных.</span><span class="sxs-lookup"><span data-stu-id="36ccf-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36ccf-116">Требования</span><span class="sxs-lookup"><span data-stu-id="36ccf-116">Requirements</span></span>  
 <span data-ttu-id="36ccf-117">**Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36ccf-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36ccf-118">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="36ccf-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36ccf-119">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36ccf-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36ccf-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36ccf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ccf-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="36ccf-121">See also</span></span>

- [<span data-ttu-id="36ccf-122">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="36ccf-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
