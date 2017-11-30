---
title: "Интерфейс IMetaDataTables"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables
helpviewer_keywords: IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c89d615fbeeff4a60eb386d58c573ee7905f538d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatables-interface"></a>Интерфейс IMetaDataTables
Предоставляет методы для хранения и извлечения сведений о метаданных в таблицах.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|Возвращает указатель на большой двоичный объект (BLOB) в индексе указанного столбца.|  
|[Метод GetBlobHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|Возвращает размер в байтах в куче больших двоичных ОБЪЕКТОВ.|  
|[Метод GetCodedTokenInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|Возвращает указатель на массив маркеров, связанных с заданным индексом строки.|  
|[Метод GetColumn](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|Возвращает указатель на значения, содержащиеся в столбце в индексе указанного столбца в таблице с индексом указанной таблицы.|  
|[GetColumnInfo-метод](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|Получает данные о заданном столбце в указанной таблице.|  
|[Метод GetGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|Возвращает идентификатор GUID из строки по указанному индексу.|  
|[Метод GetGuidHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|Возвращает размер в байтах, кучи GUID.|  
|[Метод GetNextBlob](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|Получает индекс следующего большого двоичного ОБЪЕКТА в таблице.|  
|[Метод GetNextGuid](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|Получает индекс следующего значения GUID в текущем столбце таблицы.|  
|[Метод GetNextString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|Возвращает индекс следующей строки в текущем столбце таблицы.|  
|[Метод GetNextUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|Возвращает индекс строки, содержащей Далее жестко заданная строка в текущем столбце таблицы.|  
|[Метод GetNumTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|Возвращает количество таблиц в области текущего `IMetaDataTables` экземпляра.|  
|[Метод GetRow](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|Возвращает строку с указанной строки индекса, в таблице с заданным индексом таблицы.|  
|[Метод GetString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|Возвращает строку с указанным индексом из столбца таблицы в текущей области ссылки.|  
|[Метод GetStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|Возвращает размер в байтах, кучи строк.|  
|[Метод GetTableIndex](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|Возвращает индекс для таблицы, который ссылается указанный токен.|  
|[Метод GetTableInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|Возвращает имя, размер строки, количество строк, количество столбцов и индекс столбца ключей таблицы с индексом указанной таблицы.|  
|[Метод GetUserString](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|Получает жестко заданная строка в столбце строки в текущей области по указанному индексу.|  
|[Метод GetUserStringHeapSize](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|Возвращает размер в байтах, кучи пользовательских строк.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [Интерфейс IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
