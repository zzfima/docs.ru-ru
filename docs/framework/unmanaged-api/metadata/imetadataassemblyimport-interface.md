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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905415"
---
# <a name="imetadataassemblyimport-interface"></a>Интерфейс IMetaDataAssemblyImport
Предоставляет методы для доступа и изучения содержимого манифеста сборки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CloseEnum](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|Освобождает дескриптор заданного перечислителя.|  
|[Метод EnumAssemblyRefs](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|Получает указатель интерфейса на перечислитель, содержащий `mdAssemblyRef` маркеры сборки ссылается сборка в текущей области метаданных.|  
|[Метод EnumExportedTypes](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|Получает указатель интерфейса на перечислитель, содержащий `mdExportedType` маркеры типов COM, который ссылается на сборку в текущей области метаданных.|  
|[Метод EnumFiles](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|Получает указатель интерфейса на перечислитель, содержащий `mdFile` маркеры файлы ссылается сборка в текущей области метаданных.|  
|[Метод EnumManifestResources](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|Получает указатель интерфейса на перечислитель, содержащий `mdManifestResource` маркеры ресурсов, ссылается на сборку в текущей области метаданных.|  
|[Метод FindAssembliesByName](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|Получает или задает массив `mdAssemblyRef` маркеры для сборок с указанным именем.|  
|[Метод FindExportedTypeByName](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|Получает `mdExportedType` токена для COM-типа с указанным именем.|  
|[Метод FindManifestResourceByName](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|Получает `mdManifestResource` маркера для ресурса с указанным именем.|  
|[Метод GetAssemblyFromScope](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|Получает токен для сборки в текущей области метаданных.|  
|[Метод GetAssemblyProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|Возвращает значения свойств указанной сборки.|  
|[Метод GetAssemblyRefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|Возвращает значения свойств заданного объекта `mdAssemblyRef` токена.|  
|[Метод GetExportedTypeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|Возвращает значения свойств указанного COM-типа.|  
|[Метод GetFileProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|Возвращает значения свойств указанного файла.|  
|[Метод GetManifestResourceProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|Возвращает значения свойств указанного ресурса манифеста.|  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
