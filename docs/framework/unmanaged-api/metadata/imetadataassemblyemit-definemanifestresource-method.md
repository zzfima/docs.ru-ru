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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b617e29e2df22b59114c8b978daa645de1cc6176
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186723"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="667e1-102">Метод IMetaDataAssemblyEmit::DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="667e1-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="667e1-103">Создает структуру `ManifestResource`, содержащую метаданные для указанного ресурса манифеста, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="667e1-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="667e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="667e1-104">Syntax</span></span>  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="667e1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="667e1-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="667e1-106">[in] Имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="667e1-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="667e1-107">[in] Маркер метаданных типа `mdtFile` или `mdtAssemblyRef` , сопоставляемый поставщика ресурсов.</span><span class="sxs-lookup"><span data-stu-id="667e1-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="667e1-108">Значение NULL указывает, что файл, в который внедрены метаданных — поставщик ресурсов.</span><span class="sxs-lookup"><span data-stu-id="667e1-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="667e1-109">[in] Смещение в начало ресурса в файле.</span><span class="sxs-lookup"><span data-stu-id="667e1-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="667e1-110">Для ресурсов в отдельных файлах это всегда равно нулю.</span><span class="sxs-lookup"><span data-stu-id="667e1-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="667e1-111">Если ресурс встроен в файле PE (переносимый исполняемый файл), это смещение большого двоичного ОБЪЕКТА, который начинается в расположении, указанном в файле заголовка cor.h ресурса.</span><span class="sxs-lookup"><span data-stu-id="667e1-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="667e1-112">[in] Побитовое сочетание значения флага, задайте значения свойств для определения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="667e1-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="667e1-113">[out] Указатель на токен возвращенные метаданные.</span><span class="sxs-lookup"><span data-stu-id="667e1-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="667e1-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="667e1-114">Remarks</span></span>  
 <span data-ttu-id="667e1-115">Один `ManifestResource` структура метаданных должны быть определены для каждого ресурса, который реализуется в каждом из файлов сборки.</span><span class="sxs-lookup"><span data-stu-id="667e1-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="667e1-116">Требования</span><span class="sxs-lookup"><span data-stu-id="667e1-116">Requirements</span></span>  
 <span data-ttu-id="667e1-117">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="667e1-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="667e1-118">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="667e1-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="667e1-119">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="667e1-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="667e1-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="667e1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="667e1-121">См. также</span><span class="sxs-lookup"><span data-stu-id="667e1-121">See also</span></span>

- [<span data-ttu-id="667e1-122">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="667e1-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
