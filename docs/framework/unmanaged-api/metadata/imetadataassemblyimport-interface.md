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
ms.openlocfilehash: 289e26868ff2eb9e1d97cf084e9a888815062ea4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436308"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="51a29-102">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="51a29-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="51a29-103">Предоставляет методы для доступа и изучения содержимого манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="51a29-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51a29-104">Методы</span><span class="sxs-lookup"><span data-stu-id="51a29-104">Methods</span></span>  
  
|<span data-ttu-id="51a29-105">Метод</span><span class="sxs-lookup"><span data-stu-id="51a29-105">Method</span></span>|<span data-ttu-id="51a29-106">Описание</span><span class="sxs-lookup"><span data-stu-id="51a29-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51a29-107">Метод CloseEnum</span><span class="sxs-lookup"><span data-stu-id="51a29-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="51a29-108">Освобождает дескриптор указанного перечислителя.</span><span class="sxs-lookup"><span data-stu-id="51a29-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="51a29-109">Метод EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="51a29-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="51a29-110">Возвращает указатель интерфейса на перечислитель, содержащий маркеры `mdAssemblyRef` сборок, на которые ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="51a29-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="51a29-111">Метод EnumExportedTypes</span><span class="sxs-lookup"><span data-stu-id="51a29-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="51a29-112">Возвращает указатель интерфейса на перечислитель, содержащий маркеры `mdExportedType` типов COM, на которые ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="51a29-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="51a29-113">Метод EnumFiles</span><span class="sxs-lookup"><span data-stu-id="51a29-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="51a29-114">Возвращает указатель интерфейса на перечислитель, содержащий маркеры `mdFile` файлов, на которые ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="51a29-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="51a29-115">Метод EnumManifestResources</span><span class="sxs-lookup"><span data-stu-id="51a29-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="51a29-116">Возвращает указатель интерфейса на перечислитель, содержащий маркеры `mdManifestResource` ресурсов, на которые ссылается сборка в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="51a29-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="51a29-117">Метод FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="51a29-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="51a29-118">Возвращает массив токенов `mdAssemblyRef` для сборок с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="51a29-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="51a29-119">Метод FindExportedTypeByName</span><span class="sxs-lookup"><span data-stu-id="51a29-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="51a29-120">Возвращает токен `mdExportedType` для типа COM с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="51a29-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="51a29-121">Метод FindManifestResourceByName</span><span class="sxs-lookup"><span data-stu-id="51a29-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="51a29-122">Возвращает токен `mdManifestResource` для ресурса с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="51a29-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="51a29-123">Метод GetAssemblyFromScope</span><span class="sxs-lookup"><span data-stu-id="51a29-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="51a29-124">Возвращает токен для сборки в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="51a29-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="51a29-125">Метод GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="51a29-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="51a29-126">Возвращает параметры свойства указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="51a29-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="51a29-127">Метод GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="51a29-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="51a29-128">Возвращает параметры свойства указанного маркера `mdAssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="51a29-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="51a29-129">Метод GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="51a29-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="51a29-130">Возвращает параметры свойства указанного типа COM.</span><span class="sxs-lookup"><span data-stu-id="51a29-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="51a29-131">Метод GetFileProps</span><span class="sxs-lookup"><span data-stu-id="51a29-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="51a29-132">Возвращает настройки свойств указанного файла.</span><span class="sxs-lookup"><span data-stu-id="51a29-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="51a29-133">Метод GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="51a29-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="51a29-134">Возвращает параметры свойства указанного ресурса манифеста.</span><span class="sxs-lookup"><span data-stu-id="51a29-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="51a29-135">Требования</span><span class="sxs-lookup"><span data-stu-id="51a29-135">Requirements</span></span>  
 <span data-ttu-id="51a29-136">**Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51a29-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51a29-137">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="51a29-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51a29-138">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="51a29-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="51a29-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51a29-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51a29-140">См. также</span><span class="sxs-lookup"><span data-stu-id="51a29-140">See also</span></span>

- [<span data-ttu-id="51a29-141">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="51a29-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="51a29-142">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="51a29-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
