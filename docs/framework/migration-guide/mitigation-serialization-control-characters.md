---
title: Сериализация управляющих символов с помощью DataContractJsonSerializer
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
ms.openlocfilehash: b60b78f9ee944552fafbe75754ecd29d60dd4093
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181201"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a><span data-ttu-id="72c3d-102">Устранение рисков. Сериализация управляющих символов с помощью DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="72c3d-102">Mitigation: Serialization of control characters with the DataContractJsonSerializer</span></span>

<span data-ttu-id="72c3d-103">Начиная с .NET Framework 4.7, изменился способ сериализации управляющих символов с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, чтобы соответствовать правилам ECMAScript версий 6 и 8.</span><span class="sxs-lookup"><span data-stu-id="72c3d-103">Starting with .NET Framework 4.7, the way in which control characters are serialized with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> has changed to conform to ECMAScript V6 and V8.</span></span>

## <a name="impact"></a><span data-ttu-id="72c3d-104">Последствия</span><span class="sxs-lookup"><span data-stu-id="72c3d-104">Impact</span></span>

<span data-ttu-id="72c3d-105">В .NET Framework 4.6.2 и более ранних версиях объект <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> сериализовал некоторые специальные управляющие символы, например `\b`, `\f` и `\t`, не так, как требуют стандарты ECMAScript версии 6 и версии 8.</span><span class="sxs-lookup"><span data-stu-id="72c3d-105">In .NET Framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> did not serialize some special control characters, such as `\b`, `\f`, and `\t`, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span>

<span data-ttu-id="72c3d-106">Для приложений, предназначенных для версий платформы .NET Framework, начиная с .NET Framework 4.7, сериализация таких управляющих символов совместима с ECMAScript версий 6 и 8.</span><span class="sxs-lookup"><span data-stu-id="72c3d-106">For apps that target versions of .NET Framework starting with .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span> <span data-ttu-id="72c3d-107">Это касается следующих API-интерфейсов:</span><span class="sxs-lookup"><span data-stu-id="72c3d-107">The following APIs are affected:</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a><span data-ttu-id="72c3d-108">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="72c3d-108">Mitigation</span></span>

<span data-ttu-id="72c3d-109">Для приложений, предназначенных для версий платформы .NET Framework, начиная с .NET Framework 4.7, такое поведение включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="72c3d-109">For apps that target versions of .NET Framework starting with .NET Framework 4.7, this behavior is enabled by default.</span></span>

<span data-ttu-id="72c3d-110">Если оно нежелательно, данную функцию можно отключить, добавив следующую строку в раздел `<runtime>` файла app.config или web.config:</span><span class="sxs-lookup"><span data-stu-id="72c3d-110">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

## <a name="see-also"></a><span data-ttu-id="72c3d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="72c3d-111">See also</span></span>

- [<span data-ttu-id="72c3d-112">Совместимость приложений</span><span class="sxs-lookup"><span data-stu-id="72c3d-112">Application compatibility</span></span>](application-compatibility.md)
