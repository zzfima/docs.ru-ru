---
title: Интерфейсы метаданных
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], metadata
- metadata interfaces [.NET Framework]
- interfaces (.NET Framework metadata]
ms.assetid: f5cdac93-a28c-48ef-8a19-5773376e9e7c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8a704d531b1c49ffe653009e0e90f33b7a126e91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451003"
---
# <a name="metadata-interfaces"></a><span data-ttu-id="56cf6-102">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="56cf6-102">Metadata Interfaces</span></span>
<span data-ttu-id="56cf6-103">В этом разделе описываются неуправляемые интерфейсы, обеспечивающие доступ к метаданным, предоставляемым типами, методами, полями и прочими объектами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="56cf6-103">This section describes the unmanaged interfaces that provide access to the metadata exposed by the .NET Framework types, methods, fields, and so on.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56cf6-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="56cf6-104">In This Section</span></span>  
 [<span data-ttu-id="56cf6-105">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="56cf6-105">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 <span data-ttu-id="56cf6-106">Предоставляет методы для динамической компиляции кода.</span><span class="sxs-lookup"><span data-stu-id="56cf6-106">Provides methods for dynamic code compilation.</span></span>  
  
 [<span data-ttu-id="56cf6-107">Интерфейс IHostFilter</span><span class="sxs-lookup"><span data-stu-id="56cf6-107">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)  
 <span data-ttu-id="56cf6-108">Предоставляет метод, с помощью которого узел среды выполнения помечает лексемы метаданных для обработки.</span><span class="sxs-lookup"><span data-stu-id="56cf6-108">Provides a method for the run-time host to mark metadata tokens for processing.</span></span>  
  
 [<span data-ttu-id="56cf6-109">Интерфейс IMapToken</span><span class="sxs-lookup"><span data-stu-id="56cf6-109">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)  
 <span data-ttu-id="56cf6-110">Предоставляет возможности сопоставления между импортированными и выпущенными сигнатурами метаданных.</span><span class="sxs-lookup"><span data-stu-id="56cf6-110">Provides mapping capabilities between imported and emitted metadata signatures.</span></span>  
  
 [<span data-ttu-id="56cf6-111">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="56cf6-111">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 <span data-ttu-id="56cf6-112">Предоставляет методы, поддерживающие модель самоописания, которая используется средой CLR для разрешения и потребления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="56cf6-112">Provides methods that support the self-description model used by the common language runtime (CLR) to resolve and consume resources.</span></span>  
  
 [<span data-ttu-id="56cf6-113">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="56cf6-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 <span data-ttu-id="56cf6-114">Предоставляет методы для доступа и изучения содержимого манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="56cf6-114">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
 [<span data-ttu-id="56cf6-115">Интерфейс IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="56cf6-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)  
 <span data-ttu-id="56cf6-116">Предоставляет методы для сопоставления библиотек типов с их сигнатурами метаданных и для преобразования из одних в другие.</span><span class="sxs-lookup"><span data-stu-id="56cf6-116">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
 [<span data-ttu-id="56cf6-117">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="56cf6-117">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 <span data-ttu-id="56cf6-118">`IMetaDataDispenser` устарел.</span><span class="sxs-lookup"><span data-stu-id="56cf6-118">`IMetaDataDispenser` is obsolete.</span></span> <span data-ttu-id="56cf6-119">Взамен рекомендуется использовать `IMetaDataDispenserEx`.</span><span class="sxs-lookup"><span data-stu-id="56cf6-119">Use `IMetaDataDispenserEx` instead.</span></span>  
  
 [<span data-ttu-id="56cf6-120">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="56cf6-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 <span data-ttu-id="56cf6-121">Предоставляет методы, назначающие области памяти для создания или изменения метаданных.</span><span class="sxs-lookup"><span data-stu-id="56cf6-121">Provides methods that map areas of memory for creating or modifying metadata.</span></span>  
  
 [<span data-ttu-id="56cf6-122">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="56cf6-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 <span data-ttu-id="56cf6-123">Предоставляет методы для создания, изменения и хранения метаданных о сборке в текущей заданной области.</span><span class="sxs-lookup"><span data-stu-id="56cf6-123">Provides methods to create, modify and store metadata about the assembly in the currently defined scope.</span></span>  
  
 [<span data-ttu-id="56cf6-124">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="56cf6-124">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 <span data-ttu-id="56cf6-125">Предоставляет методы для определения и изменения сигнатур метаданных методов и конструкторов с помощью параметров типа <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="56cf6-125">Provides methods for defining and modifying the metadata signatures of methods and constructors with parameters of type <xref:System.Type?displayProperty=nameWithType>.</span></span>  
  
 [<span data-ttu-id="56cf6-126">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="56cf6-126">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)  
 <span data-ttu-id="56cf6-127">Предоставляет механизм обратного вызова для сообщения об ошибках в процессе разрешения сигнатуры метаданных для сборки.</span><span class="sxs-lookup"><span data-stu-id="56cf6-127">Provides a callback mechanism for reporting errors during the resolution of the metadata signature for an assembly.</span></span>  
  
 [<span data-ttu-id="56cf6-128">Интерфейс IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="56cf6-128">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)  
 <span data-ttu-id="56cf6-129">Предоставляет методы для пометки и фильтрации лексем метаданных во избежание повторения действий, которые уже были выполнены.</span><span class="sxs-lookup"><span data-stu-id="56cf6-129">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
 [<span data-ttu-id="56cf6-130">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="56cf6-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 <span data-ttu-id="56cf6-131">Предоставляет методы для импорта типов из других сборок и манипуляций с ними.</span><span class="sxs-lookup"><span data-stu-id="56cf6-131">Provides methods for importing and manipulating types from other assemblies.</span></span>  
  
 [<span data-ttu-id="56cf6-132">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="56cf6-132">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 <span data-ttu-id="56cf6-133">Расширяет `IMetaDataImport` для обеспечения возможности работы с универсальными типами.</span><span class="sxs-lookup"><span data-stu-id="56cf6-133">Extends `IMetaDataImport` to provide the capability of working with generic types.</span></span>  
  
 [<span data-ttu-id="56cf6-134">Интерфейс IMetaDataInfo</span><span class="sxs-lookup"><span data-stu-id="56cf6-134">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 <span data-ttu-id="56cf6-135">Предоставляет метод, который получает сведения о сопоставлении метаданных из файла на диске с памятью.</span><span class="sxs-lookup"><span data-stu-id="56cf6-135">Provides a method that gets information about the mapping of metadata from an on-disk file into memory.</span></span>  
  
 [<span data-ttu-id="56cf6-136">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="56cf6-136">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 <span data-ttu-id="56cf6-137">Предоставляет методы для хранения и извлечения сведений о метаданных в таблицах.</span><span class="sxs-lookup"><span data-stu-id="56cf6-137">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
 [<span data-ttu-id="56cf6-138">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="56cf6-138">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 <span data-ttu-id="56cf6-139">Расширяет `IMetaDataTables` для включения методов работы с потоками метаданных.</span><span class="sxs-lookup"><span data-stu-id="56cf6-139">Extends `IMetaDataTables` to include methods for working with metadata streams.</span></span>  
  
 [<span data-ttu-id="56cf6-140">Интерфейс IMetaDataValidate</span><span class="sxs-lookup"><span data-stu-id="56cf6-140">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)  
 <span data-ttu-id="56cf6-141">Предоставляет методы, используемые для проверки сигнатур метаданных.</span><span class="sxs-lookup"><span data-stu-id="56cf6-141">Provides methods to use for validation of metadata signatures.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="56cf6-142">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="56cf6-142">Related Sections</span></span>  
 [<span data-ttu-id="56cf6-143">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="56cf6-143">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)  
  
 [<span data-ttu-id="56cf6-144">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="56cf6-144">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
  
 [<span data-ttu-id="56cf6-145">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="56cf6-145">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
  
 [<span data-ttu-id="56cf6-146">Объединения метаданных</span><span class="sxs-lookup"><span data-stu-id="56cf6-146">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
