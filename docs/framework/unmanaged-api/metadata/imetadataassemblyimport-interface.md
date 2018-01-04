---
title: "Интерфейс IMetaDataAssemblyImport"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport
helpviewer_keywords: IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 992b588d16bc221f6b72044da40d09fbb6894511
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="21b79-102">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="21b79-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="21b79-103">Предоставляет методы для доступа и изучения содержимого манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="21b79-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21b79-104">Методы</span><span class="sxs-lookup"><span data-stu-id="21b79-104">Methods</span></span>  
  
|<span data-ttu-id="21b79-105">Метод</span><span class="sxs-lookup"><span data-stu-id="21b79-105">Method</span></span>|<span data-ttu-id="21b79-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="21b79-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21b79-107">Метод CloseEnum</span><span class="sxs-lookup"><span data-stu-id="21b79-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="21b79-108">Освобождает дескриптор заданного перечислителя.</span><span class="sxs-lookup"><span data-stu-id="21b79-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="21b79-109">Метод EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="21b79-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="21b79-110">Получает указатель интерфейса на перечислитель, содержащий `mdAssemblyRef` маркеры сборки ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="21b79-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="21b79-111">Метод EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="21b79-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="21b79-112">Получает указатель интерфейса на перечислитель, содержащий `mdExportedType` маркеры типов COM, который ссылается на сборку в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="21b79-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="21b79-113">Метод EnumFiles</span><span class="sxs-lookup"><span data-stu-id="21b79-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="21b79-114">Получает указатель интерфейса на перечислитель, содержащий `mdFile` токены файлов ссылается на сборку в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="21b79-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="21b79-115">Метод EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="21b79-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="21b79-116">Получает указатель интерфейса на перечислитель, содержащий `mdManifestResource` маркеры ресурсов, ссылается на сборку в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="21b79-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="21b79-117">Метод FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="21b79-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="21b79-118">Получает или задает массив `mdAssemblyRef` маркеры для сборки с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="21b79-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="21b79-119">Метод FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="21b79-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="21b79-120">Возвращает `mdExportedType` маркер типа COM с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="21b79-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="21b79-121">Метод FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="21b79-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="21b79-122">Возвращает `mdManifestResource` маркера для ресурса с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="21b79-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="21b79-123">Метод GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="21b79-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="21b79-124">Получает маркер для сборки в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="21b79-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="21b79-125">Метод GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="21b79-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="21b79-126">Получает параметры свойства заданной сборки.</span><span class="sxs-lookup"><span data-stu-id="21b79-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="21b79-127">Метод GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="21b79-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="21b79-128">Получает параметры свойства заданного `mdAssemblyRef` токена.</span><span class="sxs-lookup"><span data-stu-id="21b79-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="21b79-129">Метод GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="21b79-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="21b79-130">Возвращает значения свойств заданного типа COM.</span><span class="sxs-lookup"><span data-stu-id="21b79-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="21b79-131">Метод GetFileProps</span><span class="sxs-lookup"><span data-stu-id="21b79-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="21b79-132">Возвращает значения свойств указанного файла.</span><span class="sxs-lookup"><span data-stu-id="21b79-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="21b79-133">Метод GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="21b79-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="21b79-134">Возвращает значения свойств указанного ресурса манифеста.</span><span class="sxs-lookup"><span data-stu-id="21b79-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="21b79-135">Требования</span><span class="sxs-lookup"><span data-stu-id="21b79-135">Requirements</span></span>  
 <span data-ttu-id="21b79-136">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21b79-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21b79-137">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="21b79-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21b79-138">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="21b79-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="21b79-139">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21b79-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b79-140">См. также</span><span class="sxs-lookup"><span data-stu-id="21b79-140">See Also</span></span>  
 [<span data-ttu-id="21b79-141">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="21b79-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="21b79-142">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="21b79-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
