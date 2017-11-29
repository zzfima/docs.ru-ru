---
title: "Интерфейсы метаданных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], metadata
- metadata interfaces [.NET Framework]
- interfaces (.NET Framework metadata]
ms.assetid: f5cdac93-a28c-48ef-8a19-5773376e9e7c
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 638727dae1f0f32e5c92c0da7513719bd11ae8d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="metadata-interfaces"></a>Интерфейсы метаданных
В этом разделе описываются неуправляемые интерфейсы, обеспечивающие доступ к метаданным, предоставляемым типами, методами, полями и прочими объектами .NET Framework.  
  
## <a name="in-this-section"></a>Содержание  
 [ICeeGen-интерфейс](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 Предоставляет методы для динамической компиляции кода.  
  
 [Ihostfilter-интерфейс](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)  
 Предоставляет метод, с помощью которого узел среды выполнения помечает лексемы метаданных для обработки.  
  
 [Интерфейс IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)  
 Предоставляет возможности сопоставления между импортированными и выпущенными сигнатурами метаданных.  
  
 [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 Предоставляет методы, поддерживающие модель самоописания, которая используется средой CLR для разрешения и потребления ресурсов.  
  
 [Imetadataassemblyimport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 Предоставляет методы для доступа и изучения содержимого манифеста сборки.  
  
 [Интерфейс IMetaDataConverter](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)  
 Предоставляет методы для сопоставления библиотек типов с их сигнатурами метаданных и для преобразования из одних в другие.  
  
 [IMetaDataDispenser-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 `IMetaDataDispenser` устарел. Взамен рекомендуется использовать `IMetaDataDispenserEx` .  
  
 [Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 Предоставляет методы, назначающие области памяти для создания или изменения метаданных.  
  
 [IMetaDataEmit-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 Предоставляет методы для создания, изменения и хранения метаданных о сборке в текущей заданной области.  
  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 Предоставляет методы для определения и изменения сигнатур метаданных методов и конструкторов с помощью параметров типа <xref:System.Type?displayProperty=nameWithType>.  
  
 [IMetaDataError-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)  
 Предоставляет механизм обратного вызова для сообщения об ошибках в процессе разрешения сигнатуры метаданных для сборки.  
  
 [Imetadatafilter-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)  
 Предоставляет методы для пометки и фильтрации лексем метаданных во избежание повторения действий, которые уже были выполнены.  
  
 [IMetaDataImport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 Предоставляет методы для импорта типов из других сборок и манипуляций с ними.  
  
 [IMetaDataImport2-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 Расширяет `IMetaDataImport` для обеспечения возможности работы с универсальными типами.  
  
 [Интерфейс IMetaDataInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 Предоставляет метод, который получает сведения о сопоставлении метаданных из файла на диске с памятью.  
  
 [IMetaDataTables-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 Предоставляет методы для хранения и извлечения сведений о метаданных в таблицах.  
  
 [Интерфейс IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 Расширяет `IMetaDataTables` для включения методов работы с потоками метаданных.  
  
 [Интерфейс IMetaDataValidate](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)  
 Предоставляет методы, используемые для проверки сигнатур метаданных.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Глобальные статические функции метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)  
  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
  
 [Структуры метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
  
 [Объединения метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
