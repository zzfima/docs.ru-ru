---
title: Метод IMetaDataTables::GetColumn
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: f43d4d1547cbe92f325950e1697dada83b42c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177140"
---
# <a name="imetadatatablesgetcolumn-method"></a>Метод IMetaDataTables::GetColumn
Получает указатель на значение, содержащееся в ячейке указанного столбца и строку в данной таблице.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a>Параметры

 `ixTbl`  
 (в) Индекс таблицы.  
  
 `ixCol`  
 (в) Индекс столбца в таблице.  
  
 `rid`  
 (в) Индекс строки в таблице.  
  
 `pVal`  
 (ваут) Указатель на значение в ячейке.  

## <a name="remarks"></a>Remarks

Интерпретация возвращенного значения `pVal` зависит от типа столбца. Тип столбца можно определить, позвонив по [iMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).

- Метод **GetColumn** автоматически преобразует столбцы типа **Rid** или **CodedToken** `mdToken` в полные 32-битные значения.
- Он также автоматически преобразует 8-битные или 16-битные значения в полные 32-битные значения.
- Для столбцов *типа кучи* возвращенный *pVal* будет индексом в соответствующую кучу.

| Тип столбца              | pVal содержит | Комментарий                          |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0..63)  | mdToken     | *pVal* будет содержать полный токен. Функция автоматически преобразует Rid в полный маркер. |
| `iCodedToken`..`iCodedTokenMax`<br>(64..95) | mdToken | По возвращении *pVal* будет содержать полный токен. Функция автоматически распаковывает CodedToken в полный маркер. |
| `iSHORT`(96)            | Int16         | Автоматически знак-расширенный до 32-битного.  |
| `iUSHORT`(97)           | UInt16        | Автоматически знак-расширенный до 32-битного.  |
| `iLONG`(98)             | Int32         |                                        |
| `iULONG`(99)            | UInt32        |                                        |
| `iBYTE`(100)            | Byte          | Автоматически знак-расширенный до 32-битного.  |
| `iSTRING`(101)          | Индекс струнной кучи | *pVal* — это индекс в струнную кучу. Используйте [IMetadataTables::GetString,](imetadatatables-getstring-method.md) чтобы получить фактическое значение строки столбца. |
| `iGUID`(102)            | Индекс кучи Guid | *pVal* — это индекс в кучу Guid. Используйте [IMetadataTables::GetGuid,](imetadatatables-getguid-method.md) чтобы получить фактическое значение guid столбца. |
| `iBLOB`(103)            | Индекс кучи blob | *pVal* является индексом в кучу Blob. Используйте [IMetadataTables::GetBlob,](imetadatatables-getblob-method.md) чтобы получить фактическое значение blob столбца. |
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Рамочные версии .NET**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [Интерфейс IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
