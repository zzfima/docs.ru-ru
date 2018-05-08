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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea617668a72413f3387a35fe009b37fa15d03354
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadatatablesgettableinfo-method"></a>Метод IMetaDataTables::GetTableInfo
Возвращает имя, размер строки, количество строк, количество столбцов и ключевого столбца индекса указанной таблицы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ixTbl`  
 [in] Идентификатор таблицы, свойства которого следует вернуть.  
  
 `pcbRow`  
 [out] Указатель на размер в байтах, строки в таблице.  
  
 `pcRows`  
 [out] Указатель на число строк в таблице.  
  
 `pcCols`  
 [out] Указатель на число столбцов в таблице.  
  
 `piKey`  
 [out] Указатель на индекс ключевого столбца или значение -1, если таблица не имеет ключевого столбца.  
  
 `ppName`  
 [out] Указатель на указатель на имя таблицы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [Интерфейс IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
