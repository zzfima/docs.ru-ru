---
title: Метод IMetaDataTables::GetRow
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98fc95c618a7a06f5e6c219d7707af291770c06a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781415"
---
# <a name="imetadatatablesgetrow-method"></a>Метод IMetaDataTables::GetRow
Возвращает строку по указанному индексу строки, в таблице с индексом указанной таблицы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ixTbl`  
 [in] Индекс таблицы, из которого извлекается строка.  
  
 `rid`  
 [in] Индекс строки для получения.  
  
 `ppRow`  
 [out] Указатель на указатель на строку.  
  
## <a name="remarks"></a>Примечания  
 Не рекомендуется использование этого метода, так как он не возвращает согласованные результаты. Сведения о таблице, см. в документации Common Language Infrastructure (CLI), особенно «раздел II: Определение метаданных и семантика». Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](https://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [Интерфейс IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
