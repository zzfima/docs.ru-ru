---
title: Метод EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e351c61f7e8bfc254a6fc8ea12c8a94fc393e3fc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478158"
---
# <a name="enumcustomattributes-method"></a>Метод EnumCustomAttributes
Извлекает настраиваемые атрибуты уровня сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `hEnum`  
 Дескриптор перечислителя.  
  
 `tkType`  
 Тип атрибутов, которые необходимо перечислить. Используйте `mdTokenNill` для всех атрибутов.  
  
 `rCustomValues`  
 Получает маркеры настраиваемых атрибутов.  
  
 `cMax`  
 Указывает размер `rCustomValues` массива.  
  
 `pcCustomValues`  
 При необходимости получает число значений маркера.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
