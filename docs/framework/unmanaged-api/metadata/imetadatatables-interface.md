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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b2298e2d67e8a50e11d53d864f0e78f3b549e45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645185"
---
# <a name="imetadatatables-interface"></a>Интерфейс IMetaDataTables
Предоставляет методы для хранения и извлечения сведений о метаданных в таблицах.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|Возвращает указатель на большой двоичный объект (BLOB) в индексе указанного столбца.|  
|[Метод GetBlobHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|Возвращает размер в байтах, кучи больших двоичных ОБЪЕКТОВ.|  
|[Метод GetCodedTokenInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|Получает указатель на массив токенов, связанных с заданного индекса строки.|  
|[Метод GetColumn](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|Возвращает указатель на значения, содержащиеся в столбце в индексе указанного столбца в таблице с индексом указанной таблицы.|  
|[Метод GetColumnInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|Получает данные о заданном столбце в указанной таблице.|  
|[Метод GetGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|Возвращает идентификатор GUID из строки по указанному индексу.|  
|[Метод GetGuidHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|Возвращает размер в байтах, кучи GUID.|  
|[Метод GetNextBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|Получает индекс следующий большой двоичный объект в таблице.|  
|[Метод GetNextGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|Получает индекс следующего значения GUID в текущем столбце таблицы.|  
|[Метод GetNextString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|Получает индекс следующей строки в текущем столбце таблицы.|  
|[Метод GetNextUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|Получает индекс строки, содержащей Далее жестко запрограммированные строки в текущем столбце таблицы.|  
|[Метод GetNumTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|Получает количество таблиц в области текущего `IMetaDataTables` экземпляра.|  
|[Метод GetRow](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|Возвращает строку по указанному индексу строки, в таблице с индексом указанной таблицы.|  
|[Метод GetString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|Получает строку по указанному индексу из столбца таблицы в текущей области ссылки.|  
|[Метод GetStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|Возвращает размер в байтах, кучи строк.|  
|[Метод GetTableIndex](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|Получает индекс для таблицы, который ссылается указанный токен.|  
|[Метод GetTableInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|Получает имя, размер строки, количество строк, число столбцов и ключевой столбец индекса таблицы по индексу указанной таблицы.|  
|[Метод GetUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|Получает жестко заданную строку по указанному индексу в строковый столбец в текущей области.|  
|[Метод GetUserStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|Возвращает размер в байтах, кучи строк пользователя.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Интерфейс IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
