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
ms.openlocfilehash: 4ff23330f307c10eac134048de39a6e19a67c75b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192671"
---
# <a name="idefinitionidentity-interface"></a>Интерфейс IDefinitionIdentity
Представляет уникальную подпись кода, определяющего приложение в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Получает указатель интерфейса на новый `IDefinitionIdentity` , идентичный данному `IDefinitionIdentity`, за исключением изменения указанного атрибута.|  
|`IDefinitionIdentity::EnumAttributes`|Получает указатель интерфейса на [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) , содержащий атрибуты, связанные с этим `IDefinitionIdentity`.|  
|`IDefinitionIdentity::GetAttribute`|Получает значение атрибута с указанным именем в указанном пространстве имен.|  
|`IDefinitionIdentity::SetAttribute`|Задает атрибут с указанным именем в указанное пространство имен для указанного значения.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Isolation.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
