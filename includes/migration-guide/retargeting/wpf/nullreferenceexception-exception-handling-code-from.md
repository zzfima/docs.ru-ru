---
ms.openlocfilehash: 824d75585efd40937c1a48376ec7862cba1a8fa3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235493"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a>NullReferenceException в коде обработки исключений из ImageSourceConverter.ConvertFrom

|   |   |
|---|---|
|Подробнее|Ошибка в коде обработки исключений для <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> вызывала некорректное исключение <xref:System.NullReferenceException?displayProperty=name> вместо предполагаемого исключения (<xref:System.IO.DirectoryNotFoundException?displayProperty=name> или <xref:System.IO.FileNotFoundException?displayProperty=name>). Это изменение устраняет эту ошибку. Теперь метод вызывает правильное исключение. <p/>По умолчанию все приложения, предназначенные для .NET Framework 4.6.2 и более ранних версий, по-прежнему вызывают исключение <xref:System.NullReferenceException?displayProperty=name> для обеспечения совместимости. Разработчики приложений, предназначенных для .NET Framework 4.7 и более поздних версий, должны видеть правильные исключения.|
|Предложение|Разработчики, желающие по-прежнему получать <xref:System.NullReferenceException?displayProperty=name> при работе с .NET Framework 4.7 и более поздних версий, могут добавить следующее в файл App.config приложения:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Version|4.7|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType></li></ul>|
