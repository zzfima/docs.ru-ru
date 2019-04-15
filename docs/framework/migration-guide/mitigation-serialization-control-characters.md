---
title: Устранение рисков. Сериализация управляющих символов с помощью DataContractJsonSerializer
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3355841298e039652eb81918eac98186c1a1f833
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182129"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>Устранение рисков. Сериализация управляющих символов с помощью DataContractJsonSerializer

Начиная с .NET Framework 4.7 изменился способ сериализации управляющих символов с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, чтобы соответствовать правилам ECMAScript версий 6 и 8. 
 
## <a name="impact"></a>Последствия

В .NET Framework 4.6.2 и более ранних версиях объект <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> сериализовал некоторые специальные управляющие символы, например `\b`, `\f` и `\t`, не так, как требуют стандарты ECMAScript версии 6 и версии 8.

Для приложений, предназначенных для версий платформы .NET Framework, начиная с .NET Framework 4.7, сериализация таких управляющих символов совместима с ECMAScript версий 6 и 8. Это касается следующих API-интерфейсов:

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a>Устранение рисков

Для приложений, предназначенных для версий платформы .NET Framework, начиная с .NET Framework 4.7, такое поведение включено по умолчанию.

Если оно нежелательно, данную функцию можно отключить, добавив следующую строку в раздел `<runtime>` файла app.config или web.config:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a>См. также

- [Изменения целевой платформы в .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)
