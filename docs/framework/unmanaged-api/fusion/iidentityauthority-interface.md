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
ms.openlocfilehash: 3e2d2335e37ced9139ea44092f10b19566894681
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127093"
---
# <a name="iidentityauthority-interface"></a>Интерфейс IIdentityAuthority

Управляет ключами удостоверений для объектов кода.

## <a name="methods"></a>Методы

|Метод|Описание|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|Возвращает значение, указывающее, равны ли два указанных экземпляра [идефинитионидентити](idefinitionidentity-interface.md) .|
|`IIdentityAuthority::AreReferencesEqual`|Возвращает значение, указывающее, равны ли два указанных экземпляра [иреференцеидентити](ireferenceidentity-interface.md) .|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|Возвращает значение, указывающее, равны ли два указанных представления идентификаторов определения строки.|
|`IIdentityAuthority::AreTextualReferencesEqual`|Возвращает значение, указывающее, равны ли два указанных строковых представления идентификаторов ссылки.|
|`IIdentityAuthority::CreateDefinition`|Возвращает указатель на новый экземпляр `IDefinitionIdentity`, представляющий объект кода в текущей области.|
|`IIdentityAuthority::CreateReference`|Возвращает указатель на новый экземпляр `IReferenceIdentity`, представляющий объект кода в текущей области.|
|`IIdentityAuthority::DefinitionToText`|Возвращает форматированную строковую версию указанного `IDefinitionIdentity`.|
|`IIdentityAuthority::DefinitionToTextBuffer`|Заполняет указанный буфер расширенных символов строковой версией указанного `IDefinitionIdentity`.|
|`IIdentityAuthority::DoesDefinitionMatchReference`|Возвращает значение, указывающее, ссылаются ли указанные `IDefinitionIdentity` и `IReferenceIdentity` экземпляры на один и тот же объект кода.|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|Возвращает значение, указывающее, ссылаются ли указанные строки на один и тот же объект кода.|
|`IIdentityAuthority::GenerateDefinitionKey`|Возвращает указатель на вновь созданный ключ строки для указанного `IDefinitionIdentity`.|
|`IIdentityAuthority::GenerateReferenceKey`|Возвращает указатель на вновь созданный ключ строки для указанного `IReferenceIdentity`.|
|`IIdentityAuthority::HashDefinition`|Возвращает значение хэша для указанного `IDefinitionIdentity`.|
|`IIdentityAuthority::HashReference`|Возвращает значение хэша для указанного `IReferenceIdentity`.|
|`IIdentityAuthority::ReferenceToText`|Возвращает форматированную строковую версию указанного `IReferenceIdentity`.|
|`IIdentityAuthority::ReferenceToTextBuffer`|Заполняет указанный буфер расширенных символов строковой версией указанного `IReferenceIdentity`.|
|`IIdentityAuthority::TextToDefinition`|Возвращает указатель интерфейса на экземпляр `IDefinitionIdentity`, созданный из указанной форматируемой строки.|
|`IIdentityAuthority::TextToReference`|Возвращает указатель интерфейса на экземпляр `IReferenceIdentity`, созданный из указанной форматируемой строки.|

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** Изоляция. h

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
