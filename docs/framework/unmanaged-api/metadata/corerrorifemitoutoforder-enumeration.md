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
ms.openlocfilehash: d4e9d03dcf4603f9470f8f2509050eb6f875746a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442644"
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
  
|Член|Описание|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|Указывает поведение по умолчанию, которое не выдает сообщений об ошибках.|  
|`MDErrorOutOfOrderNone`|Указывает, что компилятор не должен создавать сообщения об ошибках.|  
|`MDErrorOutOfOrderAll`|Указывает, что компилятор должен создать сообщение об ошибке, когда поле, свойство, событие, метод или параметр выпускаются в произвольном порядке.|  
|`MDMethodOutOfOrder`|Указывает, что когда метод выдается вне очереди, компилятор должен создать сообщение об ошибке.|  
|`MDFieldOutOfOrder`|Указывает, что компилятор должен создать сообщение об ошибке при поле выпускаются в произвольном порядке.|  
|`MDParamOutOfOrder`|Указывает, что компилятор должен создать сообщение об ошибке при извлечении параметра в неправильном порядке.|  
|`MDPropertyOutOfOrder`|Указывает, что когда свойство выдается вне очереди, компилятор должен создать сообщение об ошибке.|  
|`MDEventOutOfOrder`|Указывает, что компилятор должен создать сообщение об ошибке при извлечении события по порядку.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
