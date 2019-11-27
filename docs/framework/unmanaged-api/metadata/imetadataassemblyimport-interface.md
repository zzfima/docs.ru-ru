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
# <a name="imetadataassemblyimport-interface"></a>Интерфейс IMetaDataAssemblyImport
Предоставляет методы для доступа и изучения содержимого манифеста сборки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CloseEnum](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|Освобождает дескриптор указанного перечислителя.|  
|[Метод EnumAssemblyRefs](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|Возвращает указатель интерфейса на перечислитель, содержащий маркеры `mdAssemblyRef` сборок, на которые ссылается сборка в текущей области метаданных.|  
|[Метод EnumExportedTypes](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|Возвращает указатель интерфейса на перечислитель, содержащий маркеры `mdExportedType` типов COM, на которые ссылается сборка в текущей области метаданных.|  
|[Метод EnumFiles](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|Возвращает указатель интерфейса на перечислитель, содержащий маркеры `mdFile` файлов, на которые ссылается сборка в текущей области метаданных.|  
|[Метод EnumManifestResources](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|Возвращает указатель интерфейса на перечислитель, содержащий маркеры `mdManifestResource` ресурсов, на которые ссылается сборка в текущей области метаданных.|  
|[Метод FindAssembliesByName](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|Возвращает массив токенов `mdAssemblyRef` для сборок с указанным именем.|  
|[Метод FindExportedTypeByName](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|Возвращает токен `mdExportedType` для типа COM с указанным именем.|  
|[Метод FindManifestResourceByName](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|Возвращает токен `mdManifestResource` для ресурса с указанным именем.|  
|[Метод GetAssemblyFromScope](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|Возвращает токен для сборки в текущей области метаданных.|  
|[Метод GetAssemblyProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|Возвращает параметры свойства указанной сборки.|  
|[Метод GetAssemblyRefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|Возвращает параметры свойства указанного маркера `mdAssemblyRef`.|  
|[Метод GetExportedTypeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|Возвращает параметры свойства указанного типа COM.|  
|[Метод GetFileProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|Возвращает настройки свойств указанного файла.|  
|[Метод GetManifestResourceProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|Возвращает параметры свойства указанного ресурса манифеста.|  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
