---
title: Интерфейс IMetaDataConverter
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: b771b368c069a4577d266b47bfb4a5ee1935e48e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436268"
---
# <a name="imetadataconverter-interface"></a>Интерфейс IMetaDataConverter
Предоставляет методы для сопоставления библиотек типов с их сигнатурами метаданных и для преобразования из одних в другие.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetMetaDataFromTypeInfo](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|Возвращает указатель на экземпляр [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) , представляющий сигнатуру метаданных для библиотеки типов, на которую ссылается указанный экземпляр `ITypeInfo`.|  
|[Метод GetMetaDataFromTypeLib](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|Возвращает указатель на экземпляр `IMetaDataImport`, представляющий сигнатуру метаданных для библиотеки типов, представленной указанным экземпляром `ITypeLib`.|  
|[Метод GetTypeLibFromMetaData](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|Возвращает указатель на экземпляр `ITypeLib`, представляющий библиотеку типов с указанными именами модуля и библиотеки.|  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
