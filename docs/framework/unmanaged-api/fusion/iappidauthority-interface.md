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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724ee01e91f1e9f4e34d2262610152a977ed4f53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206659"
---
# <a name="iappidauthority-interface"></a>Интерфейс IAppIdAuthority
Предоставляет методы, формирующие и сравнения ключей для идентификаторов и ссылок приложения.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Получает значение, указывающее, являются ли два заданных [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) они равны. Вы можете передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION игнорировать информацию о соответствующей версии.|  
|`IAppIdAuthority::AreReferencesEqual`|Получает значение, указывающее, являются ли два заданных [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) они равны. Вы можете передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION игнорировать информацию о соответствующей версии.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Получает значение, указывающее, равны ли два определения указанную строку. Вы можете передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION игнорировать информацию о соответствующей версии.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Получает значение, указывающее, равны ли две ссылки на указанную строку. Вы можете передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION игнорировать информацию о соответствующей версии.|  
|`IAppIdAuthority::CreateDefinition`|Получает указатель интерфейса на вновь созданным `IDefinitionAppId` экземпляр, представляющий сборку в текущей области.|  
|`IAppIdAuthority::CreateReference`|Получает указатель интерфейса на только что созданный `IReferenceAppId` , представляющий сборку в текущей области.|  
|`IAppIdAuthority::DefinitionToText`|Получает строковое представление указанного `IDefinitionAppId`, используя заданные значения флага.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Получает значение, указывающее, является ли указанный `IDefinitionAppId` и `IReferenceAppId` представляют ту же сборку.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Получает значение, указывающее, представляют ли заданная строка определения и строка ссылки той же сборки.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Возвращает строковый ключ, представляющий указанный `IDefinitionAppId` экземпляра.|  
|`IAppIdAuthority::GenerateReferenceKey`|Возвращает строковый ключ, представляющий указанный `IReferenceAppId` экземпляра.|  
|`IAppIdAuthority::HashDefinition`|Возвращает хэш-ключа для указанного `IDefinitionAppId` экземпляра.|  
|`IAppIdAuthority::HashReference`|Возвращает хэш-ключа для указанного `IReferenceAppId` экземпляра.|  
|`IAppIdAuthority::ReferenceToText`|Получает строковое представление указанного `IReferenceAppId`, используя заданные значения флага.|  
|`IAppIdAuthority::TextToDefinition`|Получает указатель интерфейса на `IDefinitionAppId` экземпляр, который представляет сборки, упоминаемой в указанный ключ строки.|  
|`IAppIdAuthority::TextToReference`|Получает указатель интерфейса на `IReferenceAppId` экземпляр, который представляет сборки, упоминаемой в указанный ключ строки.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Isolation.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
