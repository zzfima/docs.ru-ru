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
ms.openlocfilehash: 263dc0f9d686440aaa23e359c26db1b4d3d09b1e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375976"
---
# <a name="iidentityauthority-interface"></a>Интерфейс IIdentityAuthority

Управляет идентификационные ключи для объектов кода.

## <a name="methods"></a>Методы

|Метод|Описание:|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|Получает значение, указывающее, являются ли два заданных [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) они равны.|
|`IIdentityAuthority::AreReferencesEqual`|Получает значение, указывающее, являются ли два заданных [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) они равны.|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|Получает значение, указывающее, равны ли два представления идентификации определение указанной строки.|
|`IIdentityAuthority::AreTextualReferencesEqual`|Получает значение, указывающее, равны ли два указанные строковые представления идентификации ссылки.|
|`IIdentityAuthority::CreateDefinition`|Возвращает указатель на новый `IDefinitionIdentity` экземпляр, представляющий объект кода в текущей области.|
|`IIdentityAuthority::CreateReference`|Возвращает указатель на новый `IReferenceIdentity` экземпляр, представляющий объект кода в текущей области.|
|`IIdentityAuthority::DefinitionToText`|Получает форматированное строковое представление указанного `IDefinitionIdentity`.|
|`IIdentityAuthority::DefinitionToTextBuffer`|Заполняет буфер указанного расширенный символ строковую версию указанного `IDefinitionIdentity`.|
|`IIdentityAuthority::DoesDefinitionMatchReference`|Получает значение, указывающее ли указанный `IDefinitionIdentity` и `IReferenceIdentity` ссылаются экземпляра на один и тот же объект кода.|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|Получает значение, указывающее, ссылаются ли указанные строки на один и тот же объект кода.|
|`IIdentityAuthority::GenerateDefinitionKey`|Возвращает указатель на только что созданный строковый ключ для указанного `IDefinitionIdentity`.|
|`IIdentityAuthority::GenerateReferenceKey`|Возвращает указатель на только что созданный строковый ключ для указанного `IReferenceIdentity`.|
|`IIdentityAuthority::HashDefinition`|Возвращает хэш-значение для указанного `IDefinitionIdentity`.|
|`IIdentityAuthority::HashReference`|Возвращает хэш-значение для указанного `IReferenceIdentity`.|
|`IIdentityAuthority::ReferenceToText`|Получает форматированное строковое представление указанного `IReferenceIdentity`.|
|`IIdentityAuthority::ReferenceToTextBuffer`|Заполняет буфер указанного расширенный символ строковую версию указанного `IReferenceIdentity`.|
|`IIdentityAuthority::TextToDefinition`|Получает указатель интерфейса на `IDefinitionIdentity` экземпляр, созданный из указанного форматированную строку.|
|`IIdentityAuthority::TextToReference`|Получает указатель интерфейса на `IReferenceIdentity` экземпляр, созданный из указанного форматированную строку.|

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** Isolation.h

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
