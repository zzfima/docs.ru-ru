---
title: Интерфейс IAppIdAuthority
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
ms.openlocfilehash: 004e4f70e3385e7a71c356cce38e64d0253dcfa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127134"
---
# <a name="iappidauthority-interface"></a>Интерфейс IAppIdAuthority
Предоставляет методы, создающие и сравнивающие ключи для удостоверений приложений и ссылок.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Возвращает значение, указывающее, равны ли два указанных экземпляра [IDefinitionAppId](idefinitionappid-interface.md) . Можно передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION, чтобы игнорировать соответствующие сведения о версии.|  
|`IAppIdAuthority::AreReferencesEqual`|Возвращает значение, указывающее, равны ли два указанных экземпляра [иреференцеаппид](ireferenceappid-interface.md) . Можно передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION, чтобы игнорировать соответствующие сведения о версии.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Возвращает значение, указывающее, равны ли два указанных строковые определения. Можно передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION, чтобы игнорировать соответствующие сведения о версии.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Возвращает значение, указывающее, равны ли две указанные строковые ссылки. Можно передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION, чтобы игнорировать соответствующие сведения о версии.|  
|`IAppIdAuthority::CreateDefinition`|Возвращает указатель интерфейса на вновь созданный экземпляр `IDefinitionAppId`, представляющий сборку в текущей области.|  
|`IAppIdAuthority::CreateReference`|Возвращает указатель интерфейса на вновь созданный `IReferenceAppId`, представляющий сборку в текущей области.|  
|`IAppIdAuthority::DefinitionToText`|Возвращает строковую версию указанного `IDefinitionAppId`, используя указанные значения флага.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Возвращает значение, указывающее, представляют ли указанные `IDefinitionAppId` и `IReferenceAppId` одну и ту же сборку.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Возвращает значение, указывающее, представляет ли указанная строка определения и ссылочную строку одну и ту же сборку.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Возвращает строковый ключ, представляющий указанный экземпляр `IDefinitionAppId`.|  
|`IAppIdAuthority::GenerateReferenceKey`|Возвращает строковый ключ, представляющий указанный экземпляр `IReferenceAppId`.|  
|`IAppIdAuthority::HashDefinition`|Возвращает хэш-ключ для указанного `IDefinitionAppId` экземпляра.|  
|`IAppIdAuthority::HashReference`|Возвращает хэш-ключ для указанного `IReferenceAppId` экземпляра.|  
|`IAppIdAuthority::ReferenceToText`|Возвращает строковую версию указанного `IReferenceAppId`, используя указанные значения флага.|  
|`IAppIdAuthority::TextToDefinition`|Возвращает указатель интерфейса на экземпляр `IDefinitionAppId`, представляющий сборку, на которую ссылается указанный ключ строки.|  
|`IAppIdAuthority::TextToReference`|Возвращает указатель интерфейса на экземпляр `IReferenceAppId`, представляющий сборку, на которую ссылается указанный ключ строки.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
