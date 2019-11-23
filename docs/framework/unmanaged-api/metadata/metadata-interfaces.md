---
title: Интерфейсы метаданных
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], metadata
- metadata interfaces [.NET Framework]
- interfaces (.NET Framework metadata]
ms.assetid: f5cdac93-a28c-48ef-8a19-5773376e9e7c
ms.openlocfilehash: 4672cb813cec4a127f7888a2273eb26c3f34c3d9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431586"
---
# <a name="metadata-interfaces"></a><span data-ttu-id="a4891-102">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="a4891-102">Metadata Interfaces</span></span>
<span data-ttu-id="a4891-103">В этом разделе описываются неуправляемые интерфейсы, обеспечивающие доступ к метаданным, предоставляемым типами, методами, полями и прочими объектами .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a4891-103">This section describes the unmanaged interfaces that provide access to the metadata exposed by the .NET Framework types, methods, fields, and so on.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a4891-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="a4891-104">In This Section</span></span>  
 [<span data-ttu-id="a4891-105">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="a4891-105">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 <span data-ttu-id="a4891-106">Предоставляет методы для динамической компиляции кода.</span><span class="sxs-lookup"><span data-stu-id="a4891-106">Provides methods for dynamic code compilation.</span></span>  
  
 [<span data-ttu-id="a4891-107">Интерфейс IHostFilter</span><span class="sxs-lookup"><span data-stu-id="a4891-107">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)  
 <span data-ttu-id="a4891-108">Предоставляет метод, с помощью которого узел среды выполнения помечает лексемы метаданных для обработки.</span><span class="sxs-lookup"><span data-stu-id="a4891-108">Provides a method for the run-time host to mark metadata tokens for processing.</span></span>  
  
 [<span data-ttu-id="a4891-109">Интерфейс IMapToken</span><span class="sxs-lookup"><span data-stu-id="a4891-109">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)  
 <span data-ttu-id="a4891-110">Предоставляет возможности сопоставления между импортированными и выпущенными сигнатурами метаданных.</span><span class="sxs-lookup"><span data-stu-id="a4891-110">Provides mapping capabilities between imported and emitted metadata signatures.</span></span>  
  
 [<span data-ttu-id="a4891-111">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="a4891-111">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 <span data-ttu-id="a4891-112">Предоставляет методы, поддерживающие модель самоописания, которая используется средой CLR для разрешения и потребления ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a4891-112">Provides methods that support the self-description model used by the common language runtime (CLR) to resolve and consume resources.</span></span>  
  
 [<span data-ttu-id="a4891-113">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="a4891-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 <span data-ttu-id="a4891-114">Предоставляет методы для доступа и изучения содержимого манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="a4891-114">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
 [<span data-ttu-id="a4891-115">Интерфейс IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="a4891-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)  
 <span data-ttu-id="a4891-116">Предоставляет методы для сопоставления библиотек типов с их сигнатурами метаданных и для преобразования из одних в другие.</span><span class="sxs-lookup"><span data-stu-id="a4891-116">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
 [<span data-ttu-id="a4891-117">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="a4891-117">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 <span data-ttu-id="a4891-118">`IMetaDataDispenser` устарел.</span><span class="sxs-lookup"><span data-stu-id="a4891-118">`IMetaDataDispenser` is obsolete.</span></span> <span data-ttu-id="a4891-119">Взамен рекомендуется использовать `IMetaDataDispenserEx`.</span><span class="sxs-lookup"><span data-stu-id="a4891-119">Use `IMetaDataDispenserEx` instead.</span></span>  
  
 [<span data-ttu-id="a4891-120">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="a4891-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 <span data-ttu-id="a4891-121">Предоставляет методы, назначающие области памяти для создания или изменения метаданных.</span><span class="sxs-lookup"><span data-stu-id="a4891-121">Provides methods that map areas of memory for creating or modifying metadata.</span></span>  
  
 [<span data-ttu-id="a4891-122">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a4891-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 <span data-ttu-id="a4891-123">Предоставляет методы для создания, изменения и хранения метаданных о сборке в текущей заданной области.</span><span class="sxs-lookup"><span data-stu-id="a4891-123">Provides methods to create, modify and store metadata about the assembly in the currently defined scope.</span></span>  
  
 [<span data-ttu-id="a4891-124">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a4891-124">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 <span data-ttu-id="a4891-125">Предоставляет методы для определения и изменения сигнатур метаданных методов и конструкторов с помощью параметров типа <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a4891-125">Provides methods for defining and modifying the metadata signatures of methods and constructors with parameters of type <xref:System.Type?displayProperty=nameWithType>.</span></span>  
  
 [<span data-ttu-id="a4891-126">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="a4891-126">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)  
 <span data-ttu-id="a4891-127">Предоставляет механизм обратного вызова для сообщения об ошибках в процессе разрешения сигнатуры метаданных для сборки.</span><span class="sxs-lookup"><span data-stu-id="a4891-127">Provides a callback mechanism for reporting errors during the resolution of the metadata signature for an assembly.</span></span>  
  
 [<span data-ttu-id="a4891-128">Интерфейс IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="a4891-128">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)  
 <span data-ttu-id="a4891-129">Предоставляет методы для пометки и фильтрации лексем метаданных во избежание повторения действий, которые уже были выполнены.</span><span class="sxs-lookup"><span data-stu-id="a4891-129">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
 [<span data-ttu-id="a4891-130">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a4891-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 <span data-ttu-id="a4891-131">Предоставляет методы для импорта типов из других сборок и манипуляций с ними.</span><span class="sxs-lookup"><span data-stu-id="a4891-131">Provides methods for importing and manipulating types from other assemblies.</span></span>  
  
 [<span data-ttu-id="a4891-132">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a4891-132">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 <span data-ttu-id="a4891-133">Расширяет `IMetaDataImport` для обеспечения возможности работы с универсальными типами.</span><span class="sxs-lookup"><span data-stu-id="a4891-133">Extends `IMetaDataImport` to provide the capability of working with generic types.</span></span>  
  
 [<span data-ttu-id="a4891-134">Интерфейс IMetaDataInfo</span><span class="sxs-lookup"><span data-stu-id="a4891-134">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 <span data-ttu-id="a4891-135">Предоставляет метод, который получает сведения о сопоставлении метаданных из файла на диске с памятью.</span><span class="sxs-lookup"><span data-stu-id="a4891-135">Provides a method that gets information about the mapping of metadata from an on-disk file into memory.</span></span>  
  
 [<span data-ttu-id="a4891-136">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="a4891-136">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 <span data-ttu-id="a4891-137">Предоставляет методы для хранения и извлечения сведений о метаданных в таблицах.</span><span class="sxs-lookup"><span data-stu-id="a4891-137">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
 [<span data-ttu-id="a4891-138">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="a4891-138">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 <span data-ttu-id="a4891-139">Расширяет `IMetaDataTables` для включения методов работы с потоками метаданных.</span><span class="sxs-lookup"><span data-stu-id="a4891-139">Extends `IMetaDataTables` to include methods for working with metadata streams.</span></span>  
  
 [<span data-ttu-id="a4891-140">Интерфейс IMetaDataValidate</span><span class="sxs-lookup"><span data-stu-id="a4891-140">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)  
 <span data-ttu-id="a4891-141">Предоставляет методы, используемые для проверки сигнатур метаданных.</span><span class="sxs-lookup"><span data-stu-id="a4891-141">Provides methods to use for validation of metadata signatures.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a4891-142">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a4891-142">Related Sections</span></span>  
 [<span data-ttu-id="a4891-143">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="a4891-143">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)  
  
 [<span data-ttu-id="a4891-144">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="a4891-144">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
  
 [<span data-ttu-id="a4891-145">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="a4891-145">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
  
 [<span data-ttu-id="a4891-146">Объединения метаданных</span><span class="sxs-lookup"><span data-stu-id="a4891-146">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
