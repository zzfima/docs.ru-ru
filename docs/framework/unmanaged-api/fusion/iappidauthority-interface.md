---
title: "Интерфейс IAppIdAuthority"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c51aac28864cba5f538f7829ba4112b141c9a3c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iappidauthority-interface"></a>Интерфейс IAppIdAuthority
Предоставляет методы, создающие и сравнения ключей для идентификаторов и ссылок приложения.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Возвращает значение, указывающее, являются ли два заданных [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) они равны. Можно передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION, чтобы не учитывать свои сведения о соответствующей версии.|  
|`IAppIdAuthority::AreReferencesEqual`|Возвращает значение, указывающее, являются ли два заданных [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) они равны. Можно передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION, чтобы не учитывать свои сведения о соответствующей версии.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Возвращает значение, указывающее, равны ли два указанных определения строки. Можно передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION, чтобы не учитывать свои сведения о соответствующей версии.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Возвращает значение, указывающее, равны ли две ссылки указанной строки. Можно передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION, чтобы не учитывать свои сведения о соответствующей версии.|  
|`IAppIdAuthority::CreateDefinition`|Получает указатель интерфейса на вновь созданный `IDefinitionAppId` экземпляр, представляющий сборку в текущей области.|  
|`IAppIdAuthority::CreateReference`|Получает указатель интерфейса на только что созданный `IReferenceAppId` , представляющий сборку в текущей области.|  
|`IAppIdAuthority::DefinitionToText`|Получает версию строки указанного `IDefinitionAppId`, используя заданные значения флага.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Возвращает значение, указывающее, является ли указанный `IDefinitionAppId` и `IReferenceAppId` представляют той же сборки.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Возвращает значение, указывающее, представляют ли заданная строка определения и строка ссылки той же сборки.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Возвращает строковый ключ, представляющий указанный `IDefinitionAppId` экземпляра.|  
|`IAppIdAuthority::GenerateReferenceKey`|Возвращает строковый ключ, представляющий указанный `IReferenceAppId` экземпляра.|  
|`IAppIdAuthority::HashDefinition`|Возвращает хэш-ключ для указанного `IDefinitionAppId` экземпляра.|  
|`IAppIdAuthority::HashReference`|Возвращает хэш-ключ для указанного `IReferenceAppId` экземпляра.|  
|`IAppIdAuthority::ReferenceToText`|Получает версию строки указанного `IReferenceAppId`, используя заданные значения флага.|  
|`IAppIdAuthority::TextToDefinition`|Возвращает указатель интерфейса `IDefinitionAppId` экземпляр, представляющий сборку ссылается указанный ключ строки.|  
|`IAppIdAuthority::TextToReference`|Возвращает указатель интерфейса `IReferenceAppId` экземпляр, представляющий сборку ссылается указанный ключ строки.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Isolation.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
