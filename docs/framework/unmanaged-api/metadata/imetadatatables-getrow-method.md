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
ms.openlocfilehash: 71f6c496816fec1a7537f5ccdfdc1b47d17da871
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177107"
---
# <a name="imetadatatablesgetrow-method"></a>Метод IMetaDataTables::GetRow
Получает строку в указанном индексе строки, в таблице в указанном индексе таблицы.  
  
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
 (в) Индекс таблицы, из которой будет извлечен ряд.  
  
 `rid`  
 (в) Индекс строки, чтобы получить.  
  
 `ppRow`  
 (ваут) Указатель на указатель на строку.  
  
## <a name="remarks"></a>Remarks  

  Мы не рекомендуем использовать этот метод, потому что он не возвращает последовательные результаты. Для получения информации о таблице GUID см. Документация доступна в Интернете; [см. ECMA C и общие стандарты языковой инфраструктуры](../../../standard/components.md#applicable-standards) и [стандартные ECMA-335 - Общая языковая инфраструктура (CLI).](http://www.ecma-international.org/publications/standards/Ecma-335.htm)  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Рамочные версии .NET**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [Интерфейс IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
