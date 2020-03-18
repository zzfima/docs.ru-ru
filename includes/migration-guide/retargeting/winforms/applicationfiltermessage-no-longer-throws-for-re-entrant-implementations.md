---
ms.openlocfilehash: 8a1e2ca0790cb62e3c2c879f2ba0bb169ef07d77
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804343"
---
### <a name="applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>Application.FilterMessage больше не создает исключение для реализаций IMessageFilter.PreFilterMessage с повторным входом

|   |   |
|---|---|
|Подробнее|До версии .NET Framework 4.6.1 при вызове <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> с <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)>, вызывающим <xref:System.Windows.Forms.Application.AddMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=name> или <xref:System.Windows.Forms.Application.RemoveMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=name> (с одновременным вызовом <xref:System.Windows.Forms.Application.DoEvents>), возникало исключение <xref:System.IndexOutOfRangeException?displayProperty=name>.<p/>Начиная с приложений, предназначенных для .NET Framework 4.6.1, это исключение больше не создается, и можно использовать фильтры с повторным входом, как описано выше.|
|Предложение|Имейте в виду, что <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> больше не вызывает исключение для поведения <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> с повторным входом, как описано выше. Будут затронуты только приложения, предназначенные для .NET Framework 4.6.1. В приложениях, предназначенных для .NET Framework 4.6.1, можно отказаться от этого изменения (или в приложениях, предназначенных для более старых платформ, можно использовать изменение) с помощью параметра совместимости [DontSupportReentrantFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md#mitigation).|
|Область|Пограничный случай|
|Version|4.6.1|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)?displayProperty=nameWithType></li></ul>|
