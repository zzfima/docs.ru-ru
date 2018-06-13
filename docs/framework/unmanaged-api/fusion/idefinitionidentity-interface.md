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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 401c23e44cc473d0a27a82a00343852693cb0f2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429349"
---
# <a name="idefinitionidentity-interface"></a>Интерфейс IDefinitionIdentity
Представляет уникальную подпись кода, определяющего приложение в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Получает указатель интерфейса на новый `IDefinitionIdentity` объекта, идентичным этому `IDefinitionIdentity`, за исключением изменения указанного атрибута.|  
|`IDefinitionIdentity::EnumAttributes`|Возвращает указатель интерфейса [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) объект, содержащий атрибуты, связанные с этим `IDefinitionIdentity`.|  
|`IDefinitionIdentity::GetAttribute`|Возвращает значение атрибута с заданным именем в указанном пространстве имен.|  
|`IDefinitionIdentity::SetAttribute`|Устанавливает атрибут с указанным именем в указанное пространство имен с указанным значением.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Isolation.h  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
