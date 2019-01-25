---
title: Перечисление CorErrorIfEmitOutOfOrder
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 084f0bbab130cd4e7334184fe9baa322c0487942
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616775"
---
# <a name="corerrorifemitoutoforder-enumeration"></a>Перечисление CorErrorIfEmitOutOfOrder
Содержит значения флагов, указывающие условия, при которых должно создаваться сообщение об ошибке при беспорядочном выводе метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|Указывает поведение по умолчанию, которое не создает сообщения об ошибках.|  
|`MDErrorOutOfOrderNone`|Указывает, что компилятору не создавать сообщения об ошибках.|  
|`MDErrorOutOfOrderAll`|Указывает, что компилятор должен создать сообщение об ошибке, когда поле, свойство, событие, метод или параметр выдается в неправильном порядке.|  
|`MDMethodOutOfOrder`|Указывает, что компилятор должен создать сообщение об ошибке, когда метод выдается в неправильном порядке.|  
|`MDFieldOutOfOrder`|Указывает, что компилятор должен создать сообщение об ошибке при извлечении поля по порядку.|  
|`MDParamOutOfOrder`|Указывает, что компилятор должен создать сообщение об ошибке при извлечении параметра в неправильном порядке.|  
|`MDPropertyOutOfOrder`|Указывает, что компилятор должен создать сообщение об ошибке при извлечении свойства в неправильном порядке.|  
|`MDEventOutOfOrder`|Указывает, что компилятор должен создать сообщение об ошибке при извлечении неупорядоченных событий.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
