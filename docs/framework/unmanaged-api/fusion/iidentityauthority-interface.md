---
title: Интерфейс IIdentityAuthority
ms.date: 03/30/2017
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 692ac4ef4fe8ea64c6a63dc2f02cc04244a842c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iidentityauthority-interface"></a>Интерфейс IIdentityAuthority
Управляет ключами идентификации для объектов кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|Возвращает значение, указывающее, являются ли два заданных [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) они равны.|  
|`IIdentityAuthority::AreReferencesEqual`|Возвращает значение, указывающее, являются ли два заданных [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) они равны.|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|Возвращает значение, указывающее, равны ли два указанные строковые представления идентификации определения.|  
|`IIdentityAuthority::AreTextualReferencesEqual`|Возвращает значение, указывающее, равны ли два указанные строковые представления идентификации ссылки.|  
|`IIdentityAuthority::CreateDefinition`|Возвращает указатель на новый `IDefinitionIdentity` экземпляр, представляющий объект кода в текущей области.|  
|`IIdentityAuthority::CreateReference`|Возвращает указатель на новый `IReferenceIdentity` экземпляр, представляющий объект кода в текущей области.|  
|`IIdentityAuthority::DefinitionToText`|Возвращает версию форматируемой строки указанного `IDefinitionIdentity`.|  
|`IIdentityAuthority::DefinitionToTextBuffer`|Заполняет буфер указанного расширенный символ строковую версию указанного `IDefinitionIdentity`.|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|Возвращает значение, указывающее, является ли указанный `IDefinitionIdentity` и `IReferenceIdentity` экземпляры ссылаются на один и тот же объект кода.|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|Возвращает значение, указывающее, ссылаются ли указанные строки на один и тот же объект кода.|  
|`IIdentityAuthority::GenerateDefinitionKey`|Возвращает указатель на только что созданный строковый ключ для указанного `IDefinitionIdentity`.|  
|`IIdentityAuthority::GenerateReferenceKey`|Возвращает указатель на только что созданный строковый ключ для указанного `IReferenceIdentity`.|  
|`IIdentityAuthority::HashDefinition`|Возвращает хэш-значение для указанного `IDefinitionIdentity`.|  
|`IIdentityAuthority::HashReference`|Возвращает хэш-значение для указанного `IreferenceIdentity`.|  
|`IIdentityAuthority::ReferenceToText`|Возвращает версию форматируемой строки указанного `IReferenceIdentity`.|  
|`IIdentityAuthority::ReferenceToTextBuffer`|Заполняет буфер указанного расширенный символ строковую версию указанного `IReferenceIdentity`.|  
|`IIdentityAuthority::TextToDefinition`|Возвращает указатель интерфейса `IDefinitionIdentity` экземпляра, созданный из указанного форматированную строку.|  
|`IIdentityAuthority::TextToReference`|Возвращает указатель интерфейса `IReferenceIdentity` экземпляра, созданный из указанного форматированную строку.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Isolation.h  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
