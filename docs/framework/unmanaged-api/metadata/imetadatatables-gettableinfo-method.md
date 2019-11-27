---
title: Метод IMetaDataTables::GetTableInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
ms.openlocfilehash: 662b628f3cc6d2d7138f56820beaccee9c5d9e81
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426657"
---
# <a name="imetadatatablesgettableinfo-method"></a>Метод IMetaDataTables::GetTableInfo
Возвращает имя, размер строки, число строк, число столбцов и индекс ключевого столбца указанной таблицы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ixTbl`  
 окне Идентификатор таблицы, свойства которой должны быть возвращены.  
  
 `pcbRow`  
 заполняет Указатель на размер строки таблицы в байтах.  
  
 `pcRows`  
 заполняет Указатель на число строк в таблице.  
  
 `pcCols`  
 заполняет Указатель на число столбцов в таблице.  
  
 `piKey`  
 заполняет Указатель на индекс ключевого столбца или значение-1, если у таблицы нет ключевого столбца.  
  
 `ppName`  
 заполняет Указатель на указатель на имя таблицы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [Интерфейс IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
