---
title: Метод IMetaDataTables::GetTableIndex
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type:
- apiref
ms.openlocfilehash: 48c38288e960ff2e1fe21f30b6eceae8eeaac2da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434854"
---
# <a name="imetadatatablesgettableindex-method"></a>Метод IMetaDataTables::GetTableIndex
Возвращает индекс для таблицы, на которую ссылается указанный токен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `token`  
 окне Токен, ссылающийся на таблицу.  
  
 `pixTbl`  
 заполняет Указатель на возвращаемый индекс для упоминаемой таблицы.  
  
## <a name="remarks"></a>Примечания  
 Мы не рекомендуем использовать этот метод, так как он не возвращает последовательные результаты. Сведения о таблице GUID см. в документации по Common Language Infrastructure (CLI), особенно в разделе "Partition II: определение метаданных и семантика". Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](https://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [Интерфейс IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
