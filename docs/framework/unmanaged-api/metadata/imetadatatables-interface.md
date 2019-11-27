---
title: Интерфейс IMetaDataTables
ms.date: 03/30/2017
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
ms.openlocfilehash: 17305f2c088dd6f479da4c823d3db0fd50c0b3d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443222"
---
# <a name="imetadatatables-interface"></a>Интерфейс IMetaDataTables
Предоставляет методы для хранения и извлечения сведений о метаданных в таблицах.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|Возвращает указатель на большой двоичный объект (BLOB) по указанному индексу столбца.|  
|[Метод GetBlobHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|Возвращает размер кучи больших двоичных объектов в байтах.|  
|[Метод GetCodedTokenInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|Возвращает указатель на массив токенов, связанных с указанным индексом строки.|  
|[Метод GetColumn](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|Возвращает указатель на значения, содержащиеся в столбце по указанному индексу столбца в таблице по указанному индексу таблицы.|  
|[Метод GetColumnInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|Получает данные о указанном столбце в указанной таблице.|  
|[Метод GetGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|Возвращает идентификатор GUID из строки по указанному индексу.|  
|[Метод GetGuidHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|Возвращает размер кучи GUID в байтах.|  
|[Метод GetNextBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|Возвращает индекс следующего большого двоичного объекта в таблице.|  
|[Метод GetNextGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|Возвращает индекс следующего значения GUID в текущем столбце таблицы.|  
|[Метод GetNextString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|Возвращает индекс следующей строки в текущем столбце таблицы.|  
|[Метод GetNextUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|Возвращает индекс строки, содержащей следующую жестко заданную строку в текущем столбце таблицы.|  
|[Метод GetNumTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|Возвращает количество таблиц в области текущего экземпляра `IMetaDataTables`.|  
|[Метод GetRow](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|Возвращает строку по указанному индексу строки в таблице по указанному индексу таблицы.|  
|[Метод GetString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|Возвращает строку по указанному индексу из столбца таблицы в области текущей ссылки.|  
|[Метод GetStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|Возвращает размер кучи строк (в байтах).|  
|[Метод GetTableIndex](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|Возвращает индекс для таблицы, на которую ссылается указанный токен.|  
|[Метод GetTableInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|Возвращает имя, размер строки, число строк, число столбцов и индекс ключевого столбца таблицы по указанному индексу таблицы.|  
|[Метод GetUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|Получает жестко заданную строку по указанному индексу в строковом столбце текущей области.|  
|[Метод GetUserStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|Возвращает размер (в байтах) кучи пользовательской строки.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Интерфейс IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
