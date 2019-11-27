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
ms.openlocfilehash: 376b9ff09ad38ca43d57fcf064458e0331da8aad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442001"
---
# <a name="imetadatatablesgetcolumn-method"></a>Метод IMetaDataTables::GetColumn
Возвращает указатель на значение, содержащееся в ячейке указанного столбца и строки в заданной таблице.  
  
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
 окне Индекс таблицы.  
  
 `ixCol`  
 окне Индекс столбца в таблице.  
  
 `rid`  
 окне Индекс строки в таблице.  
  
 `pVal`  
 заполняет Указатель на значение в ячейке.  
 
## <a name="remarks"></a>Примечания

Интерпретация значения, возвращаемого с помощью `pVal`, зависит от типа столбца. Тип столбца можно определить с помощью метода [IMetaDataTables. GetColumnInfo](imetadatatables-getcolumninfo-method.md).

- Метод **DataColumn** автоматически преобразует столбцы типа **RID** или **кодедтокен** в полные 32-разрядные значения `mdToken`.
- Он также автоматически преобразует 8-битные или 16-битные значения в полные 32-разрядные значения. 
- Для столбцов типа *кучи* возвращенный *Pval* будет индексом в соответствующей куче.

| Тип столбца              | pVal содержит | Комментарий                          |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0.. 63)  | mdToken     | *Pval* будет содержать полный маркер. Функция автоматически преобразует RID в полный маркер. |
| `iCodedToken`..`iCodedTokenMax`<br>(64.. 95) | mdToken | После возврата *Pval* будет содержать полный маркер. Функция автоматически распаковывает Кодедтокен в полную лексему. |
| `iSHORT` (96)            | Int16         | Автоматический вход в 32-разрядный.  |
| `iUSHORT` (97)           | UInt16        | Автоматический вход в 32-разрядный.  |
| `iLONG` (98)             | Int32         |                                        | 
| `iULONG` (99)            | UInt32        |                                        |
| `iBYTE` (100)            | Байт          | Автоматический вход в 32-разрядный.  |
| `iSTRING` (101)          | Индекс строковой кучи | *Pval* — это индекс в куче строк. Используйте [IMetadataTables:: GetString](imetadatatables-getstring-method.md) , чтобы получить фактическое строковое значение столбца. |
| `iGUID` (102)            | Индекс кучи GUID | *Pval* — это индекс в куче GUID. Чтобы получить действительное значение GUID столбца, используйте [IMetadataTables::](imetadatatables-getguid-method.md) DataColumn. |
| `iBLOB` (103)            | Индекс кучи больших двоичных объектов | *Pval* — это индекс в куче больших двоичных объектов. Для получения действительного значения большого двоичного объекта столбца используйте [IMetadataTables::-BLOB](imetadatatables-getblob-method.md) . |
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [Интерфейс IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
