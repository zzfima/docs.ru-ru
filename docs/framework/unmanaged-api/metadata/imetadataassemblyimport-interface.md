---
title: Интерфейс IMetaDataAssemblyImport
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 373ff0470e2403f91534df0c0ffe4039dbb0f832
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112636"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="9d53a-102">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="9d53a-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="9d53a-103">Предоставляет методы для доступа и изучения содержимого манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="9d53a-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d53a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9d53a-104">Methods</span></span>  
  
|<span data-ttu-id="9d53a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9d53a-105">Method</span></span>|<span data-ttu-id="9d53a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9d53a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d53a-107">Метод CloseEnum</span><span class="sxs-lookup"><span data-stu-id="9d53a-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="9d53a-108">Освобождает дескриптор заданного перечислителя.</span><span class="sxs-lookup"><span data-stu-id="9d53a-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="9d53a-109">Метод EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="9d53a-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="9d53a-110">Получает указатель интерфейса на перечислитель, содержащий `mdAssemblyRef` маркеры сборки ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="9d53a-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9d53a-111">Метод EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="9d53a-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="9d53a-112">Получает указатель интерфейса на перечислитель, содержащий `mdExportedType` маркеры типов COM, который ссылается на сборку в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="9d53a-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9d53a-113">Метод EnumFiles</span><span class="sxs-lookup"><span data-stu-id="9d53a-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="9d53a-114">Получает указатель интерфейса на перечислитель, содержащий `mdFile` маркеры файлы ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="9d53a-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9d53a-115">Метод EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="9d53a-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="9d53a-116">Получает указатель интерфейса на перечислитель, содержащий `mdManifestResource` маркеры ресурсов, ссылается на сборку в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="9d53a-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9d53a-117">Метод FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="9d53a-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="9d53a-118">Получает или задает массив `mdAssemblyRef` маркеры для сборок с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="9d53a-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="9d53a-119">Метод FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="9d53a-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="9d53a-120">Получает `mdExportedType` токена для COM-типа с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="9d53a-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="9d53a-121">Метод FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="9d53a-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="9d53a-122">Получает `mdManifestResource` маркера для ресурса с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="9d53a-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="9d53a-123">Метод GetAssemblyFromScop</span><span class="sxs-lookup"><span data-stu-id="9d53a-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="9d53a-124">Получает токен для сборки в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="9d53a-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9d53a-125">Метод GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="9d53a-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="9d53a-126">Возвращает значения свойств указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="9d53a-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="9d53a-127">Метод GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="9d53a-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="9d53a-128">Возвращает значения свойств заданного объекта `mdAssemblyRef` токена.</span><span class="sxs-lookup"><span data-stu-id="9d53a-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="9d53a-129">Метод GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="9d53a-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="9d53a-130">Возвращает значения свойств указанного COM-типа.</span><span class="sxs-lookup"><span data-stu-id="9d53a-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="9d53a-131">Метод GetFileProps</span><span class="sxs-lookup"><span data-stu-id="9d53a-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="9d53a-132">Возвращает значения свойств указанного файла.</span><span class="sxs-lookup"><span data-stu-id="9d53a-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="9d53a-133">Метод GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="9d53a-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="9d53a-134">Возвращает значения свойств указанного ресурса манифеста.</span><span class="sxs-lookup"><span data-stu-id="9d53a-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d53a-135">Требования</span><span class="sxs-lookup"><span data-stu-id="9d53a-135">Requirements</span></span>  
 <span data-ttu-id="9d53a-136">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d53a-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d53a-137">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9d53a-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d53a-138">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9d53a-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="9d53a-139">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9d53a-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9d53a-140">См. также</span><span class="sxs-lookup"><span data-stu-id="9d53a-140">See also</span></span>

- [<span data-ttu-id="9d53a-141">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="9d53a-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="9d53a-142">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="9d53a-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
