---
title: Интерфейс IDefinitionIdentity
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
ms.openlocfilehash: 59578e1d3a66809c86f7daad1b208df2ae09568d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108031"
---
# <a name="idefinitionidentity-interface"></a>Интерфейс IDefinitionIdentity
Представляет уникальную сигнатуру кода, определяющего приложение в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Получает указатель интерфейса на новый объект `IDefinitionIdentity`, идентичный этому `IDefinitionIdentity`, за исключением изменения указанного атрибута.|  
|`IDefinitionIdentity::EnumAttributes`|Возвращает указатель интерфейса на объект [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) , содержащий атрибуты, связанные с этим `IDefinitionIdentity`.|  
|`IDefinitionIdentity::GetAttribute`|Возвращает значение атрибута с указанным именем в указанном пространстве имен.|  
|`IDefinitionIdentity::SetAttribute`|Задает для атрибута с указанным именем в указанном пространстве имен указанное значение.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
