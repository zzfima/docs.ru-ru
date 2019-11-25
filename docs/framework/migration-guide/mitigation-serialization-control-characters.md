---
title: Устранение рисков. Сериализация управляющих символов с помощью DataContractJsonSerializer
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
ms.openlocfilehash: faa7a32766a3ea1ef9cddcdb8af8fd0dd5a6f287
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457808"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>Устранение рисков. Сериализация управляющих символов с помощью DataContractJsonSerializer

Начиная с .NET Framework 4.7 изменился способ сериализации управляющих символов с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, чтобы соответствовать правилам ECMAScript версий 6 и 8. 
 
## <a name="impact"></a>Последствия

В .NET Framework 4.6.2 и более ранних версиях объект <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> сериализовал некоторые специальные управляющие символы, например `\b`, `\f` и `\t`, не так, как требуют стандарты ECMAScript версии 6 и версии 8.

Для приложений, предназначенных для версий платформы .NET Framework, начиная с .NET Framework 4.7, сериализация таких управляющих символов совместима с ECMAScript версий 6 и 8. Это касается следующих API-интерфейсов:

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

- [Совместимость приложений](application-compatibility.md)
