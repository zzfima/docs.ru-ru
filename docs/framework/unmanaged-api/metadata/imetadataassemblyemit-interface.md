---
title: Интерфейс IMetaDataAssemblyEmit
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a66ef090a205019493e099919739867e3936873
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905233"
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="b2112-102">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="b2112-102">IMetaDataAssemblyEmit Interface</span></span>
<span data-ttu-id="b2112-103">Предоставляет методы, поддерживающие модель самоописания, которая используется средой CLR для разрешения и потребления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b2112-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2112-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b2112-104">Methods</span></span>  
  
|<span data-ttu-id="b2112-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b2112-105">Method</span></span>|<span data-ttu-id="b2112-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b2112-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2112-107">Метод DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="b2112-107">DefineAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="b2112-108">Создает структуру данных сборки, содержащую метаданные для заданной сборки, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="b2112-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b2112-109">Метод DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="b2112-109">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="b2112-110">Создает структуру `AssemblyRef`, содержащую метаданные для сборки, на которую ссылается данная сборка, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="b2112-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b2112-111">Метод DefineExportedType</span><span class="sxs-lookup"><span data-stu-id="b2112-111">DefineExportedType Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="b2112-112">Создает структуру `ExportedType`, содержащую метаданные для указанного экспортированного типа, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="b2112-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b2112-113">Метод DefineFile</span><span class="sxs-lookup"><span data-stu-id="b2112-113">DefineFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="b2112-114">Создает структуру метаданных `File`, содержащую метаданные для сборки, на которую ссылается данная сборка, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="b2112-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b2112-115">Метод DefineManifestResource</span><span class="sxs-lookup"><span data-stu-id="b2112-115">DefineManifestResource Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="b2112-116">Создает структуру `ManifestResource`, содержащую метаданные для указанного ресурса манифеста, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="b2112-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b2112-117">Метод SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="b2112-117">SetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="b2112-118">Изменяет указанную структуру метаданных `Assembly`.</span><span class="sxs-lookup"><span data-stu-id="b2112-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="b2112-119">Метод SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="b2112-119">SetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="b2112-120">Изменяет указанную структуру метаданных `AssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="b2112-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="b2112-121">Метод SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="b2112-121">SetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="b2112-122">Изменяет указанную структуру метаданных `ExportedType`.</span><span class="sxs-lookup"><span data-stu-id="b2112-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="b2112-123">Метод SetFileProps</span><span class="sxs-lookup"><span data-stu-id="b2112-123">SetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="b2112-124">Изменяет указанную структуру метаданных `File`.</span><span class="sxs-lookup"><span data-stu-id="b2112-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="b2112-125">Метод SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="b2112-125">SetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="b2112-126">Изменяет указанную структуру метаданных `ManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="b2112-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2112-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2112-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2112-128">Требования</span><span class="sxs-lookup"><span data-stu-id="b2112-128">Requirements</span></span>  
 <span data-ttu-id="b2112-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2112-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2112-130">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b2112-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2112-131">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2112-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b2112-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2112-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2112-133">См. также</span><span class="sxs-lookup"><span data-stu-id="b2112-133">See also</span></span>

- [<span data-ttu-id="b2112-134">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="b2112-134">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="b2112-135">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="b2112-135">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
