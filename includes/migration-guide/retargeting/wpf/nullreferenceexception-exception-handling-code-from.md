---
ms.openlocfilehash: 122741d13294c8b137ce48e28f0aa39c6e36265a
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859104"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a>NullReferenceException в коде обработки исключений из ImageSourceConverter.ConvertFrom

|   |   |
|---|---|
|Подробные сведения|Ошибка в коде обработки исключений для <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> вызывала некорректное исключение <xref:System.NullReferenceException?displayProperty=name> вместо предполагаемого исключения (<xref:System.IO.DirectoryNotFoundException?displayProperty=name> или <xref:System.IO.FileNotFoundException?displayProperty=name>). Это изменение устраняет эту ошибку. Теперь метод вызывает правильное исключение. <p/>По умолчанию все приложения, предназначенные для .NET Framework 4.6.2 и более ранних версий, по-прежнему вызывают исключение <xref:System.NullReferenceException?displayProperty=name> для обеспечения совместимости. Разработчики приложений, предназначенных для .NET Framework 4.7 и более поздних версий, должны видеть правильные исключения.|
|Предложение|Разработчики, желающие по-прежнему получать <xref:System.NullReferenceException?displayProperty=name> при работе с .NET Framework 4.7 и более поздних версий, могут добавить следующее в файл App.config приложения:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.7|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType></li></ul>|

