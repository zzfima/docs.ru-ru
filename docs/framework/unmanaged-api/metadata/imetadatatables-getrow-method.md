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
ms.openlocfilehash: d24dbcbdd8b0ed0736f7b59564cf72dffaa5a8f8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463956"
---
# <a name="imetadatatablesgetrow-method"></a>Метод IMetaDataTables::GetRow
Возвращает строку по указанному индексу строки, в таблице с индексом указанной таблицы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ixTbl`  
 [in] Индекс таблицы, из которого извлекается строка.  
  
 `rid`  
 [in] Индекс строки для получения.  
  
 `ppRow`  
 [out] Указатель на указатель на строку.  
  
## <a name="remarks"></a>Примечания  
 Не рекомендуется использование этого метода, так как он не возвращает согласованные результаты. Сведения о таблице см. в документации по Common Language Infrastructure (CLI), особенно «раздел II: определение метаданных и семантика». Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](https://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [Интерфейс IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
