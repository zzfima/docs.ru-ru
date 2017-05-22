---
title: "Диагностика совместимости .NET | Документы Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e481270-b62a-4cb4-8dda-5b4c5b59d61d
caps.latest.revision: 7
author: twsouthwick
ms.author: tasou
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 19006cc5f24ffc66b92e53e8174c6bd33c249679
ms.openlocfilehash: 06ebf87e02c8fd745d9c2f3a55eca329323a7d91
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="net-compatibility-diagnostics"></a>Диагностика совместимости .NET
Диагностика совместимости .NET выполняется с помощью анализаторов на базе Roslyn, которые помогают выявить проблемы совместимости приложений между версиями .NET Framework. Этот список содержит все доступные анализаторы, несмотря на то, что в рамках конкретной миграции будут действовать только некоторые из них. Анализаторы определят, какие проблемы применимы для запланированного переноса и будут исследовать только их. Сведения о проблемах, разделенных по затронутым версиям, см. в разделе [Совместимость приложений](../../../docs/framework/migration-guide/application-compatibility.md).  
  
 Каждая проблема содержит следующую информацию.  
  
-   Описание того, что изменилось по сравнению с предыдущей версией.  
  
-   Предложение представляет собой описание влияния изменения на клиентов, а также наличия доступных решений для сохранения совместимости между версиями.  
  
-   Оценка степени важности изменения. Проблемы совместимости приложений делятся на следующие категории.  
  
    |||  
    |-|-|  
    |Значительно|Значительное изменение, влияющее на большое количество приложений или требующее существенного изменения кода.|  
    |Дополнительный номер|Изменение, влияющее на небольшое количество приложений или требующее незначительного изменения кода.|  
    |Пограничный случай|Изменение, влияющее на приложения в исключительных ситуациях.|  
    |Прозрачный|Изменение без особого влияния на разработчика или пользователя приложения.|  
  
-   Версия указывает, когда изменение впервые появилось на платформе. Некоторые изменения отменяются, и этот момент также указывается.  
  
-   Тип изменения:  
  
    |||  
    |-|-|  
    |Изменение целевой платформы|Изменение влияет на приложения, которые перекомпилированы для использования в новой версии платформы .NET Framework.|  
    |Среда выполнения|Изменение влияет на существующие приложения, предназначенные для предыдущей версии платформы .NET Framework, но работающие в более поздней версии.|  
  
-   Затронутые API, если таковые имеются.  
  
-   Идентификаторы доступных средств диагностики  
  
<a name="diagnostic1"></a>   
## <a name="1-soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>1: классу SoapFormatter не удается выполнить десериализацию хэш-таблицы и подобных упорядоченных объектов коллекции  
  
|||  
|-|-|  
|Подробные сведения|Класс SoapFormatter не гарантирует, что объекты, сериализованные в одной версии .NET Framework, будут успешно десериализованы в другой версии платформы. В частности, в некоторые упорядоченные коллекции (например, Hashtable) добавлены элементы в версиях с 4.0 по 4.5, поэтому объекты этих типов не могут быть десериализованы в .NET 4.0, если бы они были сериализованы в .NET 4.5. Обратите внимание, что если сериализованные данные сериализуются и десериализуются в одной версии .NET Framework, проблемы не возникают.|  
|Предложение|Сериализацию SoapFormatter необходимо заменить сериализацией BinaryFormatter или NetDataContractSerialization, чтобы обеспечить устойчивость к изменениям .NET Framework.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%2CSystem.Runtime.Remoting.Messaging.HeaderHandler%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%2CSystem.Runtime.Remoting.Messaging.Header%5B%5D%29?displayProperty=fullName>|  
|Анализаторы|CD0001B<br /><br /> CD0001A|  
  
<a name="diagnostic3"></a>   
## <a name="3-wpf-datatemplate-elements-are-now-visible-to-uia"></a>3: элементы WPF DataTemplate теперь отображаются в UIA  
  
|||  
|-|-|  
|Подробные сведения|Ранее элементы DataTemplate не отображались в службе автоматизации пользовательского интерфейса. Начиная с версии 4.5, служба автоматизации пользовательского интерфейса будет обнаруживать эти элементы. Это полезно во многих случаях, но может нарушить выполнение тестов, зависящих от деревьев UIA, не содержащих элементы DataTemplate.|  
|Предложение|Тесты службы автоматизации пользовательского интерфейса для этого приложения может потребоваться обновить с учетом того, что теперь дерево UIA содержит ранее невидимые элементы DataTemplate. Например, тесты, которые ожидают, что некоторые элементы находятся рядом друг с другом, теперь могут ожидать, что между ними располагаются ранее невидимые элементы UIA. Или может потребоваться обновить новыми значениями тесты, которые зависят от определенных количеств или индексов для UIA элементов.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Windows.DataTemplate.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Windows.DataTemplate.%23ctor%28System.Object%29?displayProperty=fullName>|  
|Анализаторы|CD0003|  
  
<a name="diagnostic4"></a>   
## <a name="4-wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>4: выделенный текст в элементе управления TextBox WPF будет отображаться другим цветом, если текстовое поле неактивно  
  
|||  
|-|-|  
|Подробные сведения|В .NET 4.5, если элемент управления текстовым полем WPF неактивен (в нем отсутствует фокус), выбранный текст внутри поля будут отображаться цветом, отличным от того, когда элемент управления является активным.|  
|Предложение|Прежнее поведение (.NET 4.0) можно восстановить, задав свойству [FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported](https://msdn.microsoft.com/library/system.windows.frameworkcompatibilitypreferences.areinactiveselectionhighlightbrushkeyssupported\(v=vs.110\).aspx) значение false.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|Анализаторы|CD0004|  
  
<a name="diagnostic5"></a>   
## <a name="5-listtforeach-can-throw-exception-when-modifying-list-item"></a>5: List\<T>.ForEach может создавать исключение при изменении элемента списка  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET 4.5, перечислитель `List<T>.ForEach` будет создавать исключение InvalidOperationException при изменении элемента в вызывающей коллекции. Ранее исключение не создавалось, но могли возникать конфликты.|  
|Предложение|В идеальном случае следует исправить код, чтобы он не изменял списки при перечислении их элементов, поскольку эта операция небезопасна. Чтобы вернуться к предыдущему поведению, приложение должно быть предназначено для платформы .NET 4.0.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.Collections.Generic.List%601.ForEach%28System.Action%7B%600%7D%29?displayProperty=fullName>|  
|Анализаторы|CD0005|  
  
<a name="diagnostic6"></a>   
## <a name="6-systemuri-parsing-adheres-to-rfc-3987"></a>6: синтаксический анализ System.Uri соответствует стандарту RFC 3987  
  
|||  
|-|-|  
|Подробные сведения|Синтаксический анализ URI претерпел ряд изменений в .NET 4.5. Обратите внимание, что эти изменения касаются только кода, предназначенного для .NET 4.5. Если двоичный файл предназначен для .NET 4.0, будет действовать старое поведение. В синтаксический анализ URI в .NET 4.5 внесены следующие изменения.<br /><br /> Синтаксический анализ URI будет выполнять проверку нормализации и символов в соответствии с последними правилами IRI стандарта RFC 3987.<br /><br /> Форма нормализации Юникода C будет выполняться только в части узла URI.<br /><br /> Недопустимый mailto: идентификаторы URI теперь будут вызывать исключение.<br /><br /> Конечные точки в конце сегмента пути теперь сохраняются.<br /><br /> Идентификаторы URI `file://` не экранируют символ `?`.<br /><br /> Управляющие символы Юникода с `U+0080` по `U+009F` не поддерживаются.<br /><br /> Символы запятой `,` или `%2c` не отменяются автоматически.|  
|Предложение|Если необходимы старые семантики синтаксического анализа URI .NET 4.0 (часто они не требуются), их можно использовать для нацеливания в .NET 4.0. Это можно сделать с помощью TargetFrameworkAttribute в сборке или пользовательского интерфейса системы проектов Visual Studio на странице свойств проекта.|  
|Область|Значительно|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.Uri.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.Uri%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.String%2CSystem.UriKind%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.String%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.Uri%2CSystem.Uri%40%29?displayProperty=fullName>|  
|Анализаторы|CD0006D<br /><br /> CD0006C<br /><br /> CD0006F<br /><br /> CD0006E<br /><br /> CD0006A<br /><br /> CD0006G<br /><br /> CD0006B|  
  
<a name="diagnostic10"></a>   
## <a name="10-systemuri-escaping-now-supports-rfc-3986-httptoolsietforghtmlrfc3986"></a>10: экранирование System.Uri теперь поддерживает RFC 3986 (http://tools.ietf.org/html/rfc3986)  
  
|||  
|-|-|  
|Подробные сведения|Экранирование URI изменилось в .NET 4.5 для поддержки [RFC 3986](http://tools.ietf.org/html/rfc3986). Внесены следующие конкретные изменения.<br /><br /> Метод `EscapeDataString` преобразует в escape-последовательность зарезервированные символы в соответствии с RFC 3986.<br /><br /> Метод `EscapeUriString` не преобразует в escape-последовательность зарезервированные символы.<br /><br /> Метод `UnescapeDataString` не создает исключение, если ему встречается неверная escape-последовательность.<br /><br /> Преобразование незарезервированных символов в escape-символы отменяется.|  
|Предложение|Обновления приложений не зависят от UnescapeDataString для создания исключение в случае недопустимой escape-последовательности. Такие последовательности должны обнаруживаться сразу же.<br /><br /> Аналогичным образом ожидается, что экранированные и неэкранированные URI и строки данных могут отличаться в .NET 4.0 и .NET 4.5 и их не следует сравнивать версиях .NET напрямую. Их необходимо проанализировать и нормализовать в одной версии .NET перед выполнением каких-либо сравнений.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Uri.EscapeDataString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.EscapeUriString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.UnescapeDataString%28System.String%29?displayProperty=fullName>|  
|Анализаторы|CD0010A<br /><br /> CD0010B<br /><br /> CD0010C|  
  
<a name="diagnostic11"></a>   
## <a name="11-systemnetpeertopeercollaboration-unavailable-on-windows-8"></a>11: пространство имен System.Net.PeerToPeer.Collaboration недоступно в Windows 8  
  
|||  
|-|-|  
|Подробные сведения|Пространство имен System.Net.PeerToPeer.Collaboration недоступно в Windows 8.|  
|Предложение|Приложения, которые поддерживают Windows 8 или более поздние версии, должны быть обновлены, чтобы не зависеть от этого пространства имен или его элементов.|  
|Область|Значительно|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName>|  
|Анализаторы|CD0011|  
  
<a name="diagnostic12"></a>   
## <a name="12-mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>12: каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.5, каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора (объекта XmlSerializer). При попытке сериализации каталога MEF происходит вызов исключения.|  
|Предложение|Больше не следует использовать MEF для создания сериализатора.|  
|Область|Значительно|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0012|  
  
<a name="diagnostic13"></a>   
## <a name="13-missing-target-framework-moniker-results-in-40-behavior"></a>13: отсутствие моникера целевой платформы приводит к поведению версии 4.0  
  
|||  
|-|-|  
|Подробные сведения|Приложения без [TargetFrameworkAttribute](https://msdn.microsoft.com/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx), примененного на уровне сборки, будут автоматически запускаться с использованием семантики (режима совместимости) платформы .NET Framework 4.0. Для обеспечения высокого качества рекомендуется явным образом применить атрибут TargetFrameworkAttribute ко всем двоичным файлам, указывающим версию платформы .NET Framework, в которой они были созданы. Обратите внимание, что при использовании моникера целевой платформы в файле проекта MSBuild будет автоматически применять TargetFrameworkAttribute.|  
|Предложение|[TargetFrameworkAttribute](https://msdn.microsoft.com/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) должен быть предоставлен либо посредством добавления атрибута непосредственно в сборку, либо путем указания целевой платформы в [файле проекта или с помощью графического интерфейса свойств проекта Visual Studio](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx).|  
|Область|Значительно|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0013|  
  
<a name="diagnostic14"></a>   
## <a name="14-no-longer-able-to-set-enableviewstatemac-to-false"></a>14: свойству EnableViewStateMac больше невозможно задавать значение false  
  
|||  
|-|-|  
|Подробные сведения|ASP.NET теперь не позволяет разработчикам указывать `<pages enableViewStateMac="false"/>` или `<@Page EnableViewStateMac="false" %>`. Код проверки подлинности сообщения (MAC) состояния просмотра теперь принудительно применяется для всех запросов со встроенным состоянием просмотра. Затрагиваются только те приложения, в которых для свойства EnableViewStateMac явно задано значение false.|  
|Предложение|Следует считать, что свойство EnableViewStateMac имеет значение true, и возникающие ошибки MAC должны быть устранены (как описано в [этом](https://support.microsoft.com/kb/2915218) руководстве, содержащем несколько решений в зависимости от причины ошибки MAC).|  
|Область|Значительно|  
|Версия|4.5.2|  
|Тип|Среда выполнения|  
|Анализаторы|CD0014|  
  
<a name="diagnostic18"></a>   
## <a name="18-blockingcollectionttrytakefromany-does-not-throw-anymore"></a>18: BlockingCollection\<T>.TryTakeFromAny больше не вызывает исключение  
  
|||  
|-|-|  
|Подробные сведения|Метод `BlockingCollection<T>.TryTakeFromAny(BlockingCollection<T>[], T)` больше не возвращает -1 и `BlockingCollection<T>.TakeFromAny` больше не вызывает исключение, если одна из коллекций помечена как завершенная. Это изменение позволяет работать с коллекциями, если одна из коллекций пуста или завершена, но другая коллекция по-прежнему содержит элементы, которые можно извлечь.|  
|Предложение|Если метод TryTakeFromAny, возвращающий -1, и метод TakeFromAny, создающий исключение, использовались в целях управления потоком при заполнении заблокированной коллекции, такой код следует изменить для использования `.Any(b => b.IsCompleted)` для обнаружения этого условия.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Int32%29?displayProperty=fullName><br /><br /> <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|Анализаторы|CD0018A<br /><br /> CD0018B|  
  
<a name="diagnostic19"></a>   
## <a name="19-xmlschemaexception-now-sets-line-positions-properly"></a>19: свойство XmlSchemaException теперь правильно задает позиции строк  
  
|||  
|-|-|  
|Подробные сведения|Если значение LoadOptions.SetLineInfo передается методу Load и возникает ошибка проверки, свойства XmlSchemaException.LineNumber и XmlSchemaException.LinePosition теперь содержат сведения о строке.|  
|Предложение|Код обработки исключений, который предполагает, что свойства XmlSchemaException.LineNumber и XmlSchemaException.LinePosition не будут задаваться, необходимо обновить, поскольку эти свойства теперь задаются правильно при использовании SetLineInfo во время загрузки XML.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Xml.Linq.LoadOptions?displayProperty=fullName>|  
|Анализаторы|CD0019|  
  
<a name="diagnostic20"></a>   
## <a name="20-systemactivities-is-now-aptca"></a>20: System.Activities теперь является атрибутом APTCA  
  
|||  
|-|-|  
|Подробные сведения|Сборка помечена атрибутом AllowPartiallyTrustedCallersAttribute.|  
|Предложение|Производные классы не могут быть помечены атрибутом SecurityCriticalAttribute. Ранее производные классы было необходимо помечать атрибутом SecurityCriticalAttribute. Однако это изменение не должно иметь никаких реальных последствий.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0020|  
  
<a name="diagnostic21"></a>   
## <a name="21-workflow-30-types-are-obsolete"></a>21: типы рабочих процессов 3.0 устарели  
  
|||  
|-|-|  
|Подробные сведения|API-интерфейсы Windows Workflow Foundation (WWF) 3.0 (из пространства имен System.Workflow) теперь являются устаревшими.|  
|Предложение|Вместо них следует использовать новые интерфейсы API WWF 4.0 (в System.Activities). Пример использования новых интерфейсов API можно найти [здесь](https://msdn.microsoft.com/library/jj205427.aspx), а дальнейшие рекомендации доступны [здесь](http://blogs.msdn.com/b/workflowteam/archive/2012/02/08/deprecatingwf3.aspx). Кроме того, поскольку API-интерфейсы WWF 3.0 по-прежнему поддерживаются, их можно использовать, а чтобы избежать вывода предупреждения во время построения, его можно подавить или воспользоваться более старой версией компилятора.|  
|Область|Значительно|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0021|  
  
<a name="diagnostic22"></a>   
## <a name="22-some-workflow-drag-and-drop-apis-are-obsolete"></a>22: некоторые API-интерфейсы перетаскивания являются устаревшими  
  
|||  
|-|-|  
|Подробные сведения|Этот API перетаскивания рабочего процесса является устаревшим и будет вызывать предупреждения компилятора, если приложение перестроено с версии 4.5.|  
|Предложение|Следует использовать новые API [DragDropHelper](https://msdn.microsoft.com/library/system.activities.presentation.dragdrophelper\(v=vs.110\).aspx), которые поддерживают операции с несколькими объектами. Кроме того, можно подавить предупреждения сборки или избежать их вывода с помощью более старой версией компилятора. Интерфейсы API по-прежнему поддерживаются.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29?displayProperty=fullName>|  
|Анализаторы|CD0022|  
  
<a name="diagnostic23"></a>   
## <a name="23-new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>23: новые (неоднозначные) перегрузки Dispatcher.Invoke могут привести к изменению поведения  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.5 добавлены новые перегрузки в метод Dispatcher.Invoke, включающие параметр типа System.Action. Если существующий код перекомпилируется, компиляторы могут разрешить вызовы методов Dispatcher.Invoke, имеющие параметр Delegate, как вызовы методов Dispatcher.Invoke с параметром System.Action. Если вызов перегрузки Dispatcher.Invoke с параметром Delegate разрешается как вызов перегрузки Dispatcher.Invoke с параметром System.Action, возможны следующие различия в поведении.<br /><br /> При возникновении исключения события Dispatcher.UnhandledExceptionFilter и Dispatcher.UnhandledException не вызываются. Исключения обрабатываются событием UnobservedTaskException.<br /><br /> Вызовы некоторых членов, например свойства DispatcherOperation.Result, блокируются до тех пор, пока операция не будет завершена.|  
|Предложение|Чтобы избежать неоднозначности (и потенциальных различий в обработке исключений и поведениях блокировки), код, вызывающий Dispatcher.Invoke, может передать пустой object[] как второй параметр в вызов Invoke, чтобы гарантировать разрешение перегрузки метода .NET 4.0.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName>|  
|Анализаторы|CD0023|  
  
<a name="diagnostic24"></a>   
## <a name="24-encoderparameter-ctor-is-obsolete"></a>24: конструктор EncoderParameter устарел  
  
|||  
|-|-|  
|Подробные сведения|Конструктор `EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` устарел. При его использовании будут выводиться предупреждения сборки.|  
|Предложение|Несмотря на то, что конструктор `EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` будет продолжать работать, во избежание вывода устаревшего предупреждения сборки при повторной компиляции кода с помощью средств .NET 4.5 нужен следующий конструктор: [EncoderParameter.EncoderParameter(Encoder, Int32, EncoderParameterValueType, IntPtr)](https://msdn.microsoft.com/library/hh875096\(v=vs.110\).aspx).|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|Анализаторы|CD0024|  
  
<a name="diagnostic26"></a>   
## <a name="26-change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>26: изменение в поведении методов Task.WaitAll с аргументами времени ожидания  
  
|||  
|-|-|  
|Подробные сведения|В .NET 4.5 поведение методов Task.WaitAll стало более согласованным.<br /><br /> В .NET Framework 4 поведение этих методов было непоследовательным. По истечении времени ожидания, если одна или несколько задач были завершены или отменены до вызова метода, метод вызывал исключение AggregateException. По истечении времени ожидания, если ни одна задача не была завершена или отменена до вызова метода, однако одна или несколько задач входили в эти состояния после вызова метода, метод возвращал значение false.<br />В .NET Framework 4.5 эти перегрузки метода теперь возвращают false, если все задачи по-прежнему выполняются после истечения времени ожидания, и вызывают исключение AggregateException, только если входная задача была отменена (независимо от того, была ли она до или после вызова метода), а никакие другие задачи не выполняются.|  
|Предложение|Если исключение AggregateException было перехвачено с точки зрения обнаружения задачи, которая была отменена до вызова метода WaitAll, этот код должен выполнить то же обнаружение с помощью свойства IsCanceled (например, .Any(t => t.IsCanceled)), так как .NET 4.6 только создаст исключение только в том случае, если все ожидаемые задачи завершены до времени ожидания.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|Анализаторы|CD0026|  
  
<a name="diagnostic27"></a>   
## <a name="27-change-in-behavior-in-data-definition-language-ddl-apis"></a>27: изменение поведения API-интерфейсов языка определения данных (DDL)  
  
|||  
|-|-|  
|Подробные сведения|Поведение API-интерфейсов языка DDL при заданном значении AttachDBFilename изменилось следующим образом.<br /><br /> В строках подключения не требуется указывать значение Initial Catalog. Ранее требовались оба значения — AttatchDBFilename и Initial Catalog.<br /><br /> Если указаны AttatchDBFilename и Initial Catalog и данный MDF-файл существует, метод ObjectContext.DatabaseExists возвращает значение true. Раньше он возвращал значение false.<br /><br /> Если указаны AttatchDBFilename и Initial Catalog и данный MDF-файл существует, вызов метода ObjectContext.DeleteDatabase приведет к удалению файлов.<br /><br /> Если метод ObjectContext.DeleteDatabase вызывается в случае, когда в строке подключения указывается значение AttachDBFilename с несуществующим MDF-файлом и несуществующим Initial Catalog, метод вызывает исключение InvalidOperationException. Раньше он вызывал исключение SqlException.|  
|Предложение|Эти изменения облегчают создание средств и приложений, в которых используются API-интерфейсы DDL. Эти изменения могут повлиять на совместимость приложений в следующих сценариях:<br /><br /> Пользователь пишет код, который выполняет команду DROP DATABASE напрямую, а не вызывает ObjectContext.DeleteDatabase, если ObjectContext.DatabaseExists возвращает значение true. Это нарушает логику существующего кода, если база данных не присоединена, но MDF-файл существует.<br /><br /> Пользователь пишет код, который ожидает, что метод ObjectContext.DeleteDatabase вызовет исключение SqlException, а не исключение InvalidOperationException, когда Initial Catalog и MDF-файл не существуют.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0027|  
  
<a name="diagnostic28"></a>   
## <a name="28-machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>28: методы MachineKey.Encode и MachineKey.Decode устарели  
  
|||  
|-|-|  
|Подробные сведения|В настоящее время эти методы считаются устаревшими. При компиляции кода, который вызывает эти методы, создается предупреждение компилятора.|  
|Предложение|Вместо них рекомендуется использовать [MachineKey.Protect](https://msdn.microsoft.com/library/system.web.security.machinekey.protect\(v=vs.110\).aspx) и [MachineKey.Unprotect](https://msdn.microsoft.com/library/system.web.security.machinekey.unprotect\(v=vs.110\).aspx). Кроме того, можно подавить предупреждения сборки или избежать их вывода с помощью более старой версией компилятора. Интерфейсы API по-прежнему поддерживаются.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.Web.Security.MachineKey.Decode%28System.String%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName><br /><br /> <xref:System.Web.Security.MachineKey.Encode%28System.Byte%5B%5D%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName>|  
|Анализаторы|CD0028|  
  
<a name="diagnostic29"></a>   
## <a name="29-the-replace-method-in-odata-urls-is-disabled-by-default"></a>29: метод Replace в URL-адресах OData по умолчанию отключен  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.5, метод Replace в URL-адресах OData по умолчанию отключен. Если метод Replace OData отключен (теперь по умолчанию), все запросы пользователя, включая функции Replace (которые используются редко), завершатся ошибкой.|  
|Предложение|Если необходим метод Replace (который используется редко), его можно включить в [параметрах конфигурации](https://msdn.microsoft.com/library/system.data.services.configuration.dataservicesfeaturessection.replacefunction.aspx). Однако включенный метод Replace может открывать уязвимости системы безопасности, поэтому он должен использоваться только после тщательной проверки.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Data.Services.DataService%601?displayProperty=fullName>|  
|Анализаторы|CD0029|  
  
<a name="diagnostic30"></a>   
## <a name="30-systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a>30: объект System.ServiceModel.Web.WebServiceHost больше не добавляет конечную точку по умолчанию  
  
|||  
|-|-|  
|Подробные сведения|Объект System.ServiceModel.Web.WebServiceHost больше не добавляет конечную точку по умолчанию, если кодом приложения была добавлена явная конечная точка.|  
|Предложение|Если пользователи хотят иметь возможность подключаться к конечной точке по умолчанию и другие явные конечные точки были добавлены в WebServiceHost, конечные точки по умолчанию необходимо также добавить явным образом (с помощью AddDefaultEndpoints).|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.ServiceModel.Description.ServiceEndpoint%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName>|  
|Анализаторы|CD0030A<br /><br /> CD0030B|  
  
<a name="diagnostic31"></a>   
## <a name="31-eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>31: реализация EventSource.WriteEvent должна передавать WriteEvent те же параметры, которые она получила (плюс идентификатор)  
  
|||  
|-|-|  
|Подробные сведения|В среде выполнения теперь реализуется контракт, задающий следующее: класс, производный от EventSource и определяющий метод событий ETW, должен вызвать метод EventSource.WriteEvent базового класса с идентификатором события и теми же аргументами, с которыми был передан метод событий ETW.|  
|Предложение|Исключение IndexOutOfRangeException создается в том случае, если EventSource считывает данные EventSource в процессе для источника событий, нарушающего контракт.|  
|Область|Дополнительный номер|  
|Версия|4.5.1|  
|Тип|Среда выполнения|  
|Анализаторы|CD0031|  
  
<a name="diagnostic32"></a>   
## <a name="32-minfreememorypercentagetoactiveservice-is-now-respected"></a>32: параметр MinFreeMemoryPercentageToActiveService теперь учитывается  
  
|||  
|-|-|  
|Подробные сведения|Этот параметр задает минимальный объем памяти, который должен быть доступен на сервере перед активацией службы WCF. Он предназначен для предотвращения возникновения исключений OutOfMemoryException. В .NET Framework 4.5 этот параметр не оказывал никакого влияния. В .NET Framework 4.5.1 этот параметр уже используется.|  
|Предложение|Исключение возникает, если объем свободной памяти на веб-сервере меньше процентного значения, заданного параметром конфигурации. Некоторые службы WCF, которые успешно запускались и выполнялись в условиях ограниченной памяти, теперь могут завершаться ошибкой.|  
|Область|Дополнительный номер|  
|Версия|4.5.1|  
|Тип|Среда выполнения|  
|Анализаторы|CD0032|  
  
<a name="diagnostic33"></a>   
## <a name="33-xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>33: развертывание сущностей DTD XmlTextReader не может превышать 10 000 000 символов  
  
|||  
|-|-|  
|Подробные сведения|Развертывание сущностей DTD теперь не может превышать 10 000 000 символов. Загрузка XML-файлов без развертывания сущностей DTD или с ограниченным развертыванием сущностей DTD не изменяется. Файлы с сущностями DTD, которые развертываются до более чем 10 000 000 символов, не загружаются и теперь вызывают исключение.|  
|Предложение|Если ограничение развертывания сущностей DTD существенно ниже 10 000 000, значение может быть переопределено с помощью свойства [XmlReaderSettings.MaxCharactersFromEntities](https://msdn.microsoft.com/library/system.xml.xmlreadersettings.maxcharactersfromentities%28v=vs.110%29.aspx). XmlReaderSettings с правильным значением MaxCharactersFromEntity можно передать в [XmlReader.Create](https://msdn.microsoft.com/library/System.Xml.XmlReader.Create\(v=vs.110\).aspx).|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Xml.XmlTextReader.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader?displayProperty=fullName>|  
|Анализаторы|CD0033|  
  
<a name="diagnostic35"></a>   
## <a name="35-xslt-style-sheet-exception-message-changed"></a>35: изменено сообщение об исключении таблицы стилей XSLT  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.5 текст сообщения об ошибке, вызванной тем, что XSLT-файл является слишком сложным, выглядит так: "Слишком сложная таблица стилей". В предыдущих версиях сообщение об ошибке имело вид "Ошибка компиляции XSLT". Код приложений, который зависит от текста сообщения об ошибке, больше не будет работать. Однако типы исключений остаются теми же, поэтому это изменение не должно иметь никаких реальных последствий.|  
|Предложение|Обновите код приложения, зависящий от сообщения об исключении из этого условия ошибки, для ожидания нового сообщения или (что еще лучше) обновите код так, чтобы он зависел только от типа исключения ([XsltException](https://msdn.microsoft.com/library/system.xml.xsl.xsltexception\(v=vs.110\).aspx)), который не изменился.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Reflection.MethodInfo%2CSystem.Byte%5B%5D%2CSystem.Type%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName>|  
|Анализаторы|CD0035|  
  
<a name="diagnostic36"></a>   
## <a name="36-wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>36: теперь WF сериализует Expressions.Literal\<T> DateTimes по-другому (нарушает работу пользовательских средств синтаксического анализа XAML)  
  
|||  
|-|-|  
|Подробные сведения|Связанный объект [ValueSerializer](https://msdn.microsoft.com/library/system.windows.markup.valueserializer\(v=vs.110\).aspx) будет преобразовывать объект DateTime или DateTimeOffset, компоненты Second или Millisecond которого не равны нулю и (для значения DateTime) свойство DateTime.Kind которого не является неопределенным, в синтаксис элемента свойства вместо строки. Это изменение позволяет обеспечивать совместимость значений DateTime и DateTimeOffset. Пользовательские средства синтаксического анализа XAML, в которых предполагается, что входные данные XAML имеют синтаксис атрибутов, не будут работать правильно.|  
|Предложение|Это изменение позволяет обеспечивать совместимость значений DateTime и DateTimeOffset. Пользовательские средства синтаксического анализа XAML, в которых предполагается, что входные данные XAML имеют синтаксис атрибутов, не будут работать правильно.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0036|  
  
<a name="diagnostic37"></a>   
## <a name="37-new-enum-values-in-wpfs-pagerangeselection"></a>37: новые значения перечисления в перечислении PageRangeSelection WPF  
  
|||  
|-|-|  
|Подробные сведения|В перечисление [PageRangeSelection](https://msdn.microsoft.com/library/system.windows.controls.pagerangeselection\(v=vs.110\).aspx) были добавлены два новых элемента (CurrentPage и SelectedPage).|  
|Предложение|В большинстве случаев эти изменения не влияют на код пользователя. Однако следует изменить код, зависящий от конкретного числа элементов, существующих в вызовах Enum.GetNames или Enum.GetValues к типу PageRangeSelection.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>|  
|Анализаторы|CD0037|  
  
<a name="diagnostic38"></a>   
## <a name="38-wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>38: метод DispatcherSynchronizationContext.CreateCopy WPF теперь возвращает новую копию вместо текущего экземпляра  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4 метод DispatcherSynchronizationContext.CreateCopy() возвращал ссылку на текущий экземпляр главным образом в качестве оптимизации производительности. В .NET Framework 4.5 он возвращает новый экземпляр, что позволяет впервые делать заключение о том, что одинаковые ссылки указывают на то, что выполняющийся поток находится в правильном контексте синхронизации.  Маловероятно, что будет затронут код, который проверяет подлинность этих ссылок, но в связи с изменением необходимо протестировать код, который вызывает DispatcherSynchronizationContext.CreateCopy, в ходе миграции на .NET Framework 4.5 или более позднюю версию.|  
|Предложение|Имейте в виду, что теперь метод DispatcherSynchronizationContext.CreateCopy() возвращает новый объект SynchronizationContext.  Ранее код, который использовал эквивалентность ссылок, на самом деле не проверялся на нахождение в правильном контексте, но проверяется при создании в .NET 4.5 или более поздних версиях.  Хотя маловероятно, что это приведет к серьезным проблемам, проверки путей к затронутому коду должно быть достаточно для определения проблемы.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=fullName>|  
|Анализаторы|CD0038|  
  
<a name="diagnostic39"></a>   
## <a name="39-systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>39: метод System.Threading.Tasks.Task больше не создает исключение ObjectDisposedException после удаления объекта  
  
|||  
|-|-|  
|Подробные сведения|За исключением Task.IAsyncResult.AsyncWaitHandle, методы System.Threading.Tasks.Task больше не создают исключение ObjectDisposedException после удаления объекта.<br />Это изменение обеспечивает возможность использования кэшированных задач. Например, метод может возвратить кэшированную задачу для представления уже выполненной операции вместо выделения новой задачи. В предыдущих версиях платформы .NET Framework это было невозможно, поскольку любой потребитель задачи мог удалить ее, что делало ее непригодной для использования.|  
|Предложение|Имейте в виду, что методы Task больше не могут создавать исключения ObjectDisposedExceptions при удалении объекта. Если приложение зависело от этого исключения, чтобы знать, что задача была удалена, его необходимо обновить, чтобы явно проверять состояние задачи с помощью [Task.Status](https://msdn.microsoft.com/library/system.threading.tasks.task.status\(v=vs.110\).aspx).|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0039|  
  
<a name="diagnostic40"></a>   
## <a name="40-different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>40: исключения обрабатываются по-разному для методов ObjectContext.CreateDatabase и DbProviderServices.CreateDatabase  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET 4.5, если происходит сбой создания базы данных, методы `CreateDatabase` будут пытаться удалить пустую базу данных. Если эта операция выполняется успешно, будет распространяться исходное исключение `SQLException` (вместо `InvalidOperationException`, которое всегда создавалось в .NET 4.0).|  
|Предложение|При перехвате исключения InvalidOperationException во время выполнения ObjectContext.CreateDatabase или DbProviderServices.CreateDatabase теперь также следует перехватывать исключения SQL.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Data.Common.DbProviderServices.CreateDatabase%28System.Data.Common.DbConnection%2CSystem.Nullable%7BSystem.Int32%7D%2CSystem.Data.Metadata.Edm.StoreItemCollection%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|Анализаторы|CD0040|  
  
<a name="diagnostic41"></a>   
## <a name="41-objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>41: ObjectContext.Translate и ObjectContext.ExecuteStoreQuery теперь поддерживают тип перечисления  
  
|||  
|-|-|  
|Подробные сведения|В .NET 4.0 универсальный параметр `T` методов `ObjectContext.Translate` и `ObjectContext.ExecuteStoreQuery` не могли иметь тип перечисления. Теперь этот сценарий поддерживается.|  
|Предложение|Если метод Translate или ExecuteStoreQuery вызвался для типа enum в .NET 4.0, возвращалось значение "0". Если такое поведение было желательным, вызовы следовало заменять константой 0 (или его эквивалентом перечисления).|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.String%2CSystem.Data.Objects.MergeOption%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%2CSystem.String%2CSystem.Data.Objects.MergeOption%29?displayProperty=fullName>|  
|Анализаторы|CD0041|  
  
<a name="diagnostic42"></a>   
## <a name="42-enumerableemptytresult-always-returns-cached-instance"></a>42: Enumerable.Empty\<TResult> всегда возвращает кэшированный экземпляр  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET 4.5, `Enumerable.Empty` всегда возвращает кэшированный внутренний экземпляр `IEnumerable<T>`.<br /><br /> Ранее `Enumerable.Empty` кэшировал пустой `IEnumerable<T>` в момент вызова API, что означает, что в некоторых ситуациях, когда `Enumerable.Empty` вызывался быстро и параллельно, для различных вызовов API могли возвращаться разные экземпляры типа.|  
|Предложение|Так как прежнее поведение было недетерминированным, код вряд ли зависит от него. Однако в том маловероятном случае, когда выполняется сравнение пустых перечислений и ожидается, что они будут неравными, следует создать явные пустые массивы (`new T[0]`) и не использовать `Enumerable.Empty`.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=fullName>|  
|Анализаторы|CD0042|  
  
<a name="diagnostic43"></a>   
## <a name="43-httprequestcontentencoding-property-prohibits-utf7"></a>43: свойство HttpRequest.ContentEncoding запрещает кодировку UTF7  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.5, кодировка UTF-7 запрещена в теле запросов Http. Данные для приложений, которые зависят от поступающих данных UTF-7, в некоторых случаях декодируются неверно.|  
|Предложение|В идеальном случае приложения должны быть обновлены, чтобы не использовать кодировку UTF-7 в запросах Http. Кроме того, устаревшее поведение можно восстановить с помощью атрибута `aspnet:AllowUtf7RequestContentEncoding` элемента [appSettings](https://msdn.microsoft.com/library/hh975440\(v=vs.110\).aspx).|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=fullName>|  
|Анализаторы|CD0043|  
  
<a name="diagnostic44"></a>   
## <a name="44-httputilityjavascriptstringencode-escapes-ampersand"></a>44: метод HttpUtility.JavaScriptStringEncode экранирует символ амперсанда  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.5, метод JavaScriptStringEncode экранирует символ амперсанда (&).|  
|Предложение|Если в приложении предполагается прежнее поведение данного метода, можно добавить параметр aspnet:JavaScriptDoNotEncodeAmpersand в [элемент appSettings ASP.NET](https://msdn.microsoft.com/library/hh975440\(v=vs.110\).aspx) в файле конфигурации.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%2CSystem.Boolean%29?displayProperty=fullName>|  
|Анализаторы|CD0044A<br /><br /> CD0044B|  
  
<a name="diagnostic46"></a>   
## <a name="46-eventlistener-truncates-strings-with-embedded-nulls"></a>46: EventListener усекает строки с внедренными значениями NULL  
  
|||  
|-|-|  
|Подробные сведения|EventListener усекает строки с внедренными значениями NULL. Символы NULL не поддерживаются классом EventSource. Изменение влияет только на приложения, использующие EventListener для чтения данных EventSource в процессе и значения NULL в качестве разделителей.|  
|Предложение|Если возможно, следует обновить данные EventSource, чтобы не использовать внедренные символы NULL.|  
|Область|Пограничный случай|  
|Версия|4.5.1|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%2CSystem.Collections.Generic.IDictionary%7BSystem.String%2CSystem.String%7D%29?displayProperty=fullName>|  
|Анализаторы|CD0046|  
  
<a name="diagnostic48"></a>   
## <a name="48-obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>48: атрибут ObsoleteAttribute экспортируется как ObsoleteAttribute и DeprecatedAttribute в сценариях WinMD  
  
|||  
|-|-|  
|Подробные сведения|При создании библиотеки метаданных Windows (WINMD-файл) атрибут ObsoleteAttribute экспортируется как ObsoleteAttribute и Windows.Foundation.DeprecatedAttribute.|  
|Предложение|При перекомпиляции существующего исходного кода, использующего атрибут ObsoleteAttribute, могут выдаваться предупреждения при использовании кода из C++/CX или JavaScript.<br /><br /> К коду в управляемых сборках не рекомендуется применять ни ObsoleteAttribute, ни Windows.Foundation.DeprecatedAttribute, так как при сборке могут выдаваться предупреждения.|  
|Область|Пограничный случай|  
|Версия|4.5.1|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0048A<br /><br /> CD0048B|  
  
<a name="diagnostic49"></a>   
## <a name="49-resolveassemblyreference-task-now-warns-on-dependencies-with-the-wrong-architecture"></a>49: задача ResolveAssemblyReference теперь предупреждает о зависимостях с неправильной архитектурой  
  
|||  
|-|-|  
|Подробные сведения|Задача выдает предупреждение (MSB3270), которое означает, что ссылка или ее зависимости не соответствуют архитектуре приложения. Например, это происходит, если приложение, скомпилированное с параметром anycpu, содержит 86-разрядную ссылку. Такой сценарий может привести к сбою приложения во время выполнения (в этом случае: если приложение развертывается как 64-разрядный процесс).|  
|Предложение|Существует две области влияния.<br /><br /> Во время перекомпиляции выдаются предупреждения, которые отсутствовали при компиляции в предыдущей версии MSBuild. Однако поскольку в предупреждении указан возможный источник ошибки среды выполнения, его следует проверить.<br /><br /> Если предупреждения считаются ошибками, приложение скомпилировано не будет.|  
|Область|Дополнительный номер|  
|Версия|4.5.1|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0049|  
  
<a name="diagnostic51"></a>   
## <a name="51-wpf-textbox-defaults-to-undo-limit-of-100"></a>51: ограничение отмены по умолчанию для текстового поля WPF равно 100  
  
|||  
|-|-|  
|Подробные сведения|В .NET 4.5 ограничение отмены по умолчанию для текстового поля WPF равно 100 (в отличие от неограниченного в .NET 4.0).|  
|Предложение|Если ограничение отмены, равное 100, слишком низкое, ограничение можно задать явным образом с помощью свойства UndoLimit текстового поля.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|Анализаторы|CD0051|  
  
<a name="diagnostic55"></a>   
## <a name="55-exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>55: исключения во время обработки без наблюдения в классе System.Threading.Tasks.Task больше не распространяются на поток метода завершения  
  
|||  
|-|-|  
|Подробные сведения|Поскольку класс System.Threading.Tasks.Task представляет асинхронную операцию, он перехватывает все исключения невысокой серьезности, происходящие во время асинхронной обработки. В .NET Framework 4.5, если исключение не наблюдается и код не ожидает задачу, исключение больше не распространяется на поток метода завершения и не приводит к сбою процесса во время сборки мусора. Это изменение повышает надежность приложений, использующих класс Task для выполнения асинхронной обработки без наблюдения.|  
|Предложение|Если приложение зависит от асинхронных исключений без наблюдения, распространяющихся на поток метода завершения, можно восстановить прежнее поведение, предоставив соответствующий обработчик для события [TaskScheduler.UnobservedTaskException](https://msdn.microsoft.com/library/system.threading.tasks.taskscheduler.unobservedtaskexception\(v=vs.110\).aspx) или задав значение для [элемента конфигурации среды выполнения](https://msdn.microsoft.com/library/jj160346%28v=vs.110%29.aspx).|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Threading.Tasks.Task.Run%28System.Action%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Action%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start%28System.Threading.Tasks.TaskScheduler%29?displayProperty=fullName>|  
|Анализаторы|CD0055|  
  
<a name="diagnostic58"></a>   
## <a name="58-iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a>58: чтобы результирующая задача завершилась, реализация свойства IAsyncResult.CompletedSynchronously должна быть правильной  
  
|||  
|-|-|  
|Подробные сведения|При вызове TaskFactory.FromAsync реализация свойства IAsyncResult.CompletedSynchronously должна быть правильной, чтобы результирующая задача завершилась. То есть свойство должно возвращать значение true, если (и только если) реализация завершилась синхронно. Раньше свойство не проверялось.|  
|Предложение|Если реализация IAsyncResult правильно возвращает значение true для свойства CompletedSynchronusly только тогда, когда задача завершилась синхронно, нарушения работы не будет. Пользователи должны проверять принадлежащие им реализации IAsyncResult (если таковые имеются), чтобы убедиться, что они правильно определяют синхронное завершение задачи.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName>|  
|Анализаторы|CD0058|  
  
<a name="diagnostic59"></a>   
## <a name="59-log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>59: имя файла журнала, созданного методом ObjectContext.CreateDatabase, изменилось в соответствии со спецификациями SQL Server  
  
|||  
|-|-|  
|Подробные сведения|При вызове метода CreateDatabase либо напрямую, либо с использованием Code First с поставщиком SqlClient и значения AttachDBFilename в строке подключения он создает файл журнала с именем filename_log.ldf вместо filename.ldf (где filename — имя файла, заданное значением AttachDBFilename). Это изменение улучшает отладку, предоставляя файл журнала, имя которого соответствует спецификациям SQL Server.|  
|Предложение|Если имя файла журнала важно для приложения, приложение следует обновить для использования стандартного формата имени файла _log.ldf.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|Анализаторы|CD0059|  
  
<a name="diagnostic60"></a>   
## <a name="60-pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>60: событие Page.LoadComplete больше не заставляет элемент управления System.Web.UI.WebControls.EntityDataSource вызывать привязку данных  
  
|||  
|-|-|  
|Подробные сведения|Событие `Page.LoadComplete` больше не заставляет элемент управления System.Web.UI.WebControls.EntityDataSource вызывать привязку данных для изменений в параметрах создания, обновления или удаления. Это изменение исключает лишнее обращение к базе данных, не допускает сброса значений элементов управления и позволяет получить поведение, согласованное с другими элементами управления данными, такими как SqlDataSource и ObjectDataSource. Это изменение дает другое поведение в том маловероятном случае, когда в приложении предполагается вызов привязки данных в событии `Page.LoadComplete`.|  
|Предложение|Если есть необходимость в привязке данных, вручную вызовите ее в событии, которое возникает раньше в обратной передаче.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0060|  
  
<a name="diagnostic61"></a>   
## <a name="61-webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>61: метод WebUtility.HtmlDecode больше не декодирует недопустимую входную последовательность  
  
|||  
|-|-|  
|Подробные сведения|По умолчанию методы декодирования больше не декодируют недопустимую входную последовательность в недопустимую строку UTF-16. Вместо этого они возвращают исходные входные данные.|  
|Предложение|Изменение в выходных данных декодера может иметь значение, только если в строках хранятся двоичные данные, а не данные UTF-16. Чтобы явно контролировать это поведение, присвойте атрибуту `aspnet:AllowRelaxedUnicodeDecoding` элемента [appSettings](https://msdn.microsoft.com/library/ms228154\(v=vs.110\).aspx) значение true, чтобы разрешить устаревшее поведение, или значение false, чтобы разрешить текущее поведение.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Net.WebUtility.HtmlDecode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.HtmlDecode%28System.String%2CSystem.IO.TextWriter%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.UrlDecode%28System.String%29?displayProperty=fullName>|  
|Анализаторы|CD0061|  
  
<a name="diagnostic63"></a>   
## <a name="63-apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>63: приложения, опубликованные с помощью ClickOnce с использованием сертификата подписи кода SHA-256, могут завершиться ошибкой в Windows 2003  
  
|||  
|-|-|  
|Подробные сведения|Исполняемый файл подписывается с помощью SHA256. Ранее он подписывался с помощью SHA1 независимо от того, какой использовался сертификат подписи кода: SHA-1 или SHA-256. Применение:<br /><br /> Все приложения, собранные с помощью Visual Studio 2012 или более поздней версии.<br /><br /> Приложения, собранные с помощью Visual Studio 2010 или более ранней версии в системах с установленной платформой .NET Framework 4.5.<br /><br /> Кроме того, при наличии .NET Framework 4.5 или более поздней версии манифест ClickOnce также подписывается с помощью SHA-256 для сертификатов SHA-256 независимо от версии .NET Framework, в которой проводилась компиляция.|  
|Предложение|Изменение подписи исполняемого файла ClickOnce влияет только на системы Windows Server 2003; потребуется установка компонента из статьи базы знаний 938397.<br /><br /> Изменение подписи манифеста с SHA-256, даже если целевая платформа приложения — .NET Framework 4.0 или более ранней версии, вводит зависимость среды выполнения для .NET Framework 4.5 или более поздней версии.|  
|Область|Пограничный случай|  
|Версия|4.5-4.6|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0063|  
  
<a name="diagnostic68"></a>   
## <a name="68-dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>68: DbParameter.Precision и DbParameter.Scale теперь являются открытыми виртуальными членами  
  
|||  
|-|-|  
|Подробные сведения|DbParameter.Precision и DbParameter.Scale реализованы как открытые виртуальные свойства. Они заменяют соответствующие явные реализации интерфейса — DbParameter.IDbDataParameter.Precision и DbParameter.IDbDataParameter.Scale.|  
|Предложение|При повторном создании поставщика базы данных ADO.NET эти различия потребуют применения ключевого слова override к свойствам Precision и Scale. Это требуется только в случае повторного создания компонентов; существующие двоичные файлы будут продолжать работать.|  
|Область|Дополнительный номер|  
|Версия|4.5.1|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.Data.Common.DbParameter.Precision?displayProperty=fullName><br /><br /> <xref:System.Data.Common.DbParameter.Scale?displayProperty=fullName>|  
|Анализаторы|CD0068|  
  
<a name="diagnostic73"></a>   
## <a name="73-dataobjectgetdata-now-retrieves-data-as-utf-8"></a>73: DataObject.GetData теперь получает данные в кодировке UTF-8  
  
|||  
|-|-|  
|Подробные сведения|Для приложений, предназначенных для NET Framework 4, а также для выполняющихся в .NET Framework 4.5.1 или более ранних версиях, DataObject.GetData получает HTML-данные в виде строки ASCII. В результате символы, не относящиеся к ASCII (т. е. символы с кодами ASCII больше 0x7F), представляются двумя случайными символами.<br /><br /> Для приложений, предназначенных для NET Framework 4.5 и более поздней версии и выполняемых в .NET Framework 4.5.2, `DataObject.GetData` получает HTML-данные в формате UTF-8, который правильно представляет символы с кодами более 0x7F.|  
|Предложение|Если реализован обходной путь для проблемы с кодировкой HTML-строк (например, явная кодировка HTML-строки, полученной из буфера обмена, путем ее передачи в метод UTF8Encoding.GetString) и выполняется изменение целевой платформы приложения с версии 4 на версию 4.5, этот обходной путь необходимо удалить.<br /><br /> Если по какой-либо причине требуется старое поведение, приложение может быть предназначено для .NET Framework 4.0.|  
|Область|Пограничный случай|  
|Версия|4.5.2|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.Windows.DataObject.GetData%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.Type%29?displayProperty=fullName>|  
|Анализаторы|CD0073|  
  
<a name="diagnostic75"></a>   
## <a name="75-targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>75: TargetFrameworkName для домена приложения по умолчанию больше не принимает значение NULL по умолчанию, если оно не задано  
  
|||  
|-|-|  
|Подробные сведения|Свойство TargetFrameworkName имело ранее значение NULL в домене приложения по умолчанию, если оно не было задано явно. Начиная с 4.6, свойство TargetFrameworkName для домена приложения по умолчанию будет иметь значение по умолчанию, полученное из свойства TargetFrameworkAttribute (если оно доступно). Домены приложений не по умолчанию будут по-прежнему наследовать свойство TargetFrameworkName от домена приложения по умолчанию (который не будет по умолчанию иметь значение NULL в 4.6), если оно явно не переопределено.|  
|Предложение|Следует обновить код так, чтобы он не зависел от `AppDomainSetup.TargetFrameworkName`, принимающего п умолчанию значение NULL. Если требуется, чтобы свойство продолжало принимать значение NULL, ему можно явно присвоить это значение.|  
|Область|Пограничный случай|  
|Версия|4.6|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>|  
|Анализаторы|CD0075B<br /><br /> CD0075A|  
  
<a name="diagnostic76"></a>   
## <a name="76-x509certificate2tostringbool-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>76: теперь метод X509Certificate2.ToString(bool) не создает исключение, когда .NET не удается обработать сертификат  
  
|||  
|-|-|  
|Подробные сведения|Ранее этот метод создавал исключение, если значение true передавалось в параметр verbose и были установлены сертификаты, не поддерживаемые .NET Framework. Теперь метод будет выполняться успешно и возвращать допустимую строку, в которой пропущены недоступные части сертификата.|  
|Предложение|Любой код, зависящий от X509Certificate2.ToString(bool), следует обновить для ожидания того, что в некоторых случаях, когда ранее API возвращал исключение, в возвращаемой строке могут отсутствовать некоторые данные сертификата (например, открытый ключ, закрытый ключ и расширения).|  
|Область|Пограничный случай|  
|Версия|4.6|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|  
|Анализаторы|CD0076|  
  
<a name="diagnostic77"></a>   
## <a name="77-reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>77: объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM  
  
|||  
|-|-|  
|Подробные сведения|Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM. Затронуты следующие типы:<br /><br /> Assembly<br /><br /> MemberInfo (и его производные типы, включая FieldInfo, MethodInfo, Type и TypeInfo)<br /><br /> MethodBody<br /><br /> Модуль<br /><br /> ParameterInfo.<br /><br /> Вызовы `IMarshal` объекта возвращают `E_NOINTERFACE`.|  
|Предложение|Обновите код маршалинга для работы с объектами без отражения|  
|Область|Дополнительный номер|  
|Версия|4.6|  
|Тип|Среда выполнения|  
|Анализаторы|CD0077|  
  
<a name="diagnostic78"></a>   
## <a name="78-contentdisposition-datetimes-returns-slightly-different-string"></a>78: ContentDisposition DateTime возвращает немного другую строку  
  
|||  
|-|-|  
|Подробные сведения|Строковые представления ContentDispositions были обновлены, начиная с 4.6, чтобы всегда представлять компонент часа DateTime с двумя цифрами. Это сделано в соответствии с [RFC822](http://www.ietf.org/rfc/rfc0822.txt) и [RFC2822](http://www.ietf.org/rfc/rfc2822.txt). В результате `ContentDisposition.ToString` возвращает немного другую строку в 4.6 в сценариях, где один из элементов времени расположения имел значение, предшествующее 10:00. Обратите внимание, что ContentDispositions иногда сериализуются посредством преобразования в строки, поэтому следует проверить все операции ContentDisposition ToString, сериализации или вызовы GetHashCode.|  
|Предложение|Не ожидается, что строковые представления ContentDispositions из разных версий .NET Framework будут правильно сравниваться друг с другом. Если возможно, перед сравнением преобразуйте строки обратно в ContentDispositions.|  
|Область|Дополнительный номер|  
|Версия|4.6|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=fullName><br /><br /> <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=fullName>|  
|Анализаторы|CD0078|  
  
<a name="diagnostic82"></a>   
## <a name="82-workflowdesignerload-doesnt-remove-symbol-property"></a>82: WorkflowDesigner.Load не удаляет свойство символа  
  
|||  
|-|-|  
|Подробные сведения|При выборе целевой версии платформы .NET Framework 4.5 в конструкторе рабочих процессов и загрузке повторно размещаемого рабочего процесса 3.5 с помощью метода WorkflowDesigner.Load() во время сохранения рабочего процесса создается исключение XamlDuplicateMemberException.|  
|Предложение|Эта ошибка возникает только при нацеливании на .NET Framework 4.5 в конструкторе рабочих процессов, поэтому ее можно устранить, установив `WorkflowDesigner.Context.Services.GetService<DesignerConfigurationService>().TargetFrameworkName` в 4.0 .NET Framework.<br /><br /> Кроме того, эту проблему можно устранить, используя для загрузки метод [WorkflowContext.Load(string)](https://msdn.microsoft.com/library/ee425926\(v=vs.110\).aspx) вместо метода [WorkflowDesigner.Load()](https://msdn.microsoft.com/library/ee403482\(v=vs.110\).aspx).|  
|Область|Значительно|  
|Версия|4.5-4.5.2|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=fullName>|  
|Анализаторы|CD0082|  
  
<a name="diagnostic83"></a>   
## <a name="83-sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>83: SqlConnection.Open завершается ошибкой в Windows 7 при наличии базовых поставщиков услуг или многоуровневых поставщиков услуг Winsock, не относящихся к IFS  
  
|||  
|-|-|  
|Подробные сведения|SqlConneciton.Open и OpenAsync завершаются ошибкой в .NET Framework 4.5, если они запущены на компьютере Windows 7 при наличии базовых поставщиков услуг или многоуровневых поставщиков услуг Winsock, не относящихся к IFS.<br /><br /> Чтобы определить, установлен ли поставщик BSP или поставщик LSP, не относящийся к IFS, используйте команду `netsh WinSock Show Catalog` и просмотрите каждый возвращаемый элемент `Winsock Catalog Provider Entry`. Если в качестве значения флагов службы задано `0x20000` бит, поставщик использует маркеры IFS и будет работать правильно. Если флаг `0x20000` бит снят (значение не задано), это поставщик BSP или LSP, не относящийся к IFS.|  
|Предложение|Это ошибка исправлена в .NET Framework 4.5.2, поэтому ее можно избежать путем обновления .NET Framework. Кроме того, ее можно избежать, удалив все установленные поставщики LSP Winsock, не относящиеся к IFS.|  
|Область|Дополнительный номер|  
|Версия|4.5-4.5.2|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=fullName><br /><br /> <xref:System.Data.SqlClient.SqlConnection.OpenAsync%28System.Threading.CancellationToken%29?displayProperty=fullName>|  
|Анализаторы|CD0083|  
  
<a name="diagnostic84"></a>   
## <a name="84-icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>84: в .NET 4.5 изменено поведение события ICommand.CanExecuteChanged  
  
|||  
|-|-|  
|Подробные сведения|В платформе .NET Framework 4.5 событие CanExecuteChangedEvent игнорировалось до тех пор, пока отправителем события был один и тот же объект, что и объект, создавший событие. Эта ошибка была исправлена в обслуживающих обновлениях .NET Framework 4.5.|  
|Предложение|Эта ошибка была исправлена в обслуживающих выпусках .NET Framework 4.5, поэтому ее можно избежать, убедившись, что платформа .NET Framework не требует обновления, или выполнив обновление до .NET Framework 4.5.1. Кроме того, код приложения, использующий ICommand, можно изменить, чтобы отправитель, вызывающий команду CanExecuteChanged, совпадал с объектом, создающим событие.|  
|Область|Дополнительный номер|  
|Версия|4.5-4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=fullName>|  
|Анализаторы|CD0084|  
  
<a name="diagnostic85"></a>   
## <a name="85-some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>85: некоторые интерфейсы API .NET создают первый экземпляр (обрабатываемый) EntryPointNotFoundExceptions  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.5 несколько методов .NET начали создавать первый экземпляр EntryPointNotFoundExceptions. Эти исключения обрабатывались в .NET Framework, но могли нарушать работу службы автоматизации тестирования, которая не ожидала первых экземпляров исключений. Те же интерфейсы API препятствуют работе некоторых сценариев ApiVerifier, если включен тест HighVersionLie.|  
|Предложение|Этой ошибки можно избежать путем обновления до .NET Framework 4.5.1. Кроме того, службу автоматизации тестирования можно обновить, чтобы она не прерывала свое выполнение при создании первого экземпляра EntryPointNotFoundExceptions.|  
|Область|Пограничный случай|  
|Версия|4.5-4.5.1|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%29?displayProperty=fullName>|  
|Анализаторы|CD0085|  
  
<a name="diagnostic86"></a>   
## <a name="86-scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>86: прокрутка TreeView в WPF или сгруппированный ListBox в VirtualizingStackPanel может привести к зависанию  
  
|||  
|-|-|  
|Подробные сведения|В версии .NET Framework 4.5 прокрутка TreeView WPF на панели виртуализированного стека может привести к зависанию при наличии полей в области просмотра (между элементами в TreeView, например, или в элементе ItemsPresenter). Кроме того, в некоторых случаях элементы разных размеров в представлении могут привести к нестабильности даже при отсутствии полей.|  
|Предложение|Этой ошибки можно избежать путем обновления до .NET Framework 4.5.1. Кроме того, можно удалить поля из коллекций представлений (таких как TreeView) на панелях виртуализированных стеков, если все содержащиеся в них элементы имеют одинаковый размер.|  
|Область|Значительно|  
|Версия|4.5-4.5.1|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Windows.Controls.VirtualizingPanel.SetIsVirtualizing%28System.Windows.DependencyObject%2CSystem.Boolean%29?displayProperty=fullName>|  
|Анализаторы|CD0086<br /><br /> CD0086|  
  
<a name="diagnostic89"></a>   
## <a name="89-typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>89: Type.IsAssignableFrom возвращает неверный результат для универсальных переменных с ограничениями  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.5 Type.IsAssignableFrom неправильно возвратит `false` во всех случаях для некоторых универсальных типов с ограничениями.|  
|Предложение|Эта проблема была исправлена в обновлении обслуживания. Чтобы устранить эту проблему, обновите .NET Framework 4.5 или выполните обновление до .NET Framework 4.5.1 или более поздней версии. Кроме того, не используйте IsAssignableFrom с универсальными типами, которые имеют ограничения по универсальным параметрам. В качестве возможного решения воспользуйтесь API отражения.|  
|Область|Дополнительный номер|  
|Версия|4.5-4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Type.IsAssignableFrom%28System.Type%29?displayProperty=fullName>|  
|Анализаторы|CD0089<br /><br /> CD0089|  
  
<a name="diagnostic91"></a>   
## <a name="91-entityframework-60-loads-very-slowly-in-apps-launched-from-visual-studio"></a>91: EntityFramework 6.0 очень медленно загружается в приложениях, запускаемых из Visual Studio  
  
|||  
|-|-|  
|Подробные сведения|Запуск приложения из среды Visual Studio 2013, которая использует EntityFramework 6.0, может проходить очень медленно.|  
|Предложение|Эта проблема решена в EntityFramework 6.0.2. Обновите EntityFramework, чтобы избежать проблем с производительностью.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0091|  
  
<a name="diagnostic92"></a>   
## <a name="92-multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>92: изменены интервалы многострочного текстового поля ASP.NET при использовании AntiXSSEncoder  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.0 между строками многострочного текстового поля при обратной передаче вставлялись дополнительные строки, если использовался `AntiXSSEncoder`. В .NET Framework 4.5 эти дополнительные разрывы строк отсутствуют только в том случае, если веб-приложение предназначено для .NET 4.5|  
|Предложение|Имейте в виду, что в веб-приложениях 4.0, перенаправленных на .NET 4.5, многострочные текстовые поля могут быть усовершенствованы, чтобы больше не вставлять дополнительные разрывы строк. Если это нежелательно, для приложения, выполняющегося в .NET Framework 4.5, можно сохранить старое поведение путем изменения версии платформы на .NET Framework 4.0.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0092|  
  
<a name="diagnostic95"></a>   
## <a name="95-concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>95: ConcurrentQueue\<T>.TryPeek может возвращать ошибочные значения NULL в выходном параметре  
  
|||  
|-|-|  
|Подробные сведения|В некоторых сценариях с несколькими потоками `ConcurentQueue<T>.TryPeek` может возвращать значение true, но заполнять выходной параметр значением NULL (вместо правильного значения).|  
|Предложение|Эта проблема решена в EntityFramework 4.5.1. Чтобы устранить проблему, выполните обновление до этой версии платформы.|  
|Область|Значительно|  
|Версия|4.5-4.5.1|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek%28%600%40%29?displayProperty=fullName>|  
|Анализаторы|CD0095|  
  
<a name="diagnostic98"></a>   
## <a name="98-multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>98: можно упорядочить несколько элементов в одной ячейке TableLayoutPanel  
  
|||  
|-|-|  
|Подробные сведения|Если в .NET Framework 4.5 несколько элементов помещаются в одну и ту же ячейку TableLayoutPanel, они могут отображаться в порядке, отличном от порядка отображения в .NET Framework 4.0.|  
|Предложение|Это поведение было восстановлено в обновлении обслуживания для .NET Framework 4.5. Чтобы устранить эту проблему, обновите .NET Framework 4.5 или выполните обновление до .NET Framework 4.5.1 или более поздней версии. Кроме того, избегайте неоднозначных случаев, когда несколько элементов находятся в одной и той же ячейке TableLayourPanel.|  
|Область|Дополнительный номер|  
|Версия|4.5-4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Windows.Forms.TableLayoutControlCollection.Add%28System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|Анализаторы|CD0098|  
  
<a name="diagnostic100"></a>   
## <a name="100-foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>100: переменная-итератор Foreach теперь ограничена областью итерации, поэтому используется другая семантика захвата замыкания (в C# 5)  
  
|||  
|-|-|  
|Подробные сведения|Начиная с C# 5 (Visual Studio 2012), переменные-итераторы foreach действуют в рамках итерации. Это может привести к нарушению работы, если код ранее зависел от переменных, не включаемых в замыкание foreach. Признаком этого изменения будет то, что переменная-итератор, переданная делегату, будет рассматриваться как значение, существовавшее во время создания делегата, а не как значение, которое существовало во время вызова делегата.|  
|Предложение|В идеале следует обновить код для ожидания нового поведения компилятора. Если требуются старые семантики, переменную-итератор можно заменить отдельной переменной, которая явным образом помещается за пределами области цикла.|  
|Область|Значительно|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0100|  
  
<a name="diagnostic101"></a>   
## <a name="101-htmltextwriter-does-not-render-br-element-correctly"></a>101: HtmlTextWriter неправильно отображает элемент \`<br/\>  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.6, при вызове `HtmlTextWriter.RenderBeginTag()` и `HtmlTextWriter.RenderEndTag()` с элементом `<BR />` правильно вставляется только один `<BR />` (вместо двух).|  
|Предложение|Если приложение зависит от дополнительного тега `<BR />`, `HtmlTextWriter.RenderBeginTag()` следует вызвать второй раз. Обратите внимание, что это изменение поведения влияет только на приложения, предназначенные для .NET Framework 4.6, поэтому другим вариантом является нацеливание на предыдущую версию платформы .NET Framework для получения старого поведения.|  
|Область|Пограничный случай|  
|Версия|4.6|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>|  
|Анализаторы|CD0101|  
  
<a name="diagnostic104"></a>   
## <a name="104-calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>104: вызов Items.Refresh для ListBox, ListView или DataGrid в WPF с выбранным элементом может привести к появлению в элементе повторяющихся записей  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.5 вызов ListBox.Items.Refresh из кода, когда элементы выбраны в ListBox, может привести к дублированию выбранных элементов в списке. Такая же проблема возникает с ListView и DataGrid. Эта проблема устранена в EntityFramework 4.6.|  
|Предложение|Эту проблему можно решить программным путем, отменив выбор элементов до вызова метода Refresh и затем повторно выбрав их после завершения вызова. Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.|  
|Область|Дополнительный номер|  
|Версия|4.5-4.6|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName>|  
|Анализаторы|CD0104|  
  
<a name="diagnostic105"></a>   
## <a name="105-etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>105: EventListeners трассировки событий Windows не выполняют запись событий от поставщиков с явными ключевыми словами (например, от поставщика TPL)  
  
|||  
|-|-|  
|Подробные сведения|EventListeners трассировки событий Windows с пустой маской ключевого слова неправильно записывают события от поставщиков с явными ключевыми словами. В платформе .NET Framework 4.5 поставщик TPL начал предоставлять явные ключевые слова и привел к возникновению этой проблемы. В .NET Framework 4.6 EventListeners были обновлены, чтобы больше не вызывать эту проблему.|  
|Предложение|Чтобы решить эту проблему, замените вызовы EnableEvents(eventSource, level) на вызовы перегрузки EnableEvents, которая явным образом задает маску "любые ключевые слова" для использования: `EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))`.<br /><br /> Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.|  
|Область|Пограничный случай|  
|Версия|4.5-4.6|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName>|  
|Анализаторы|CD0105|  
  
<a name="diagnostic109"></a>   
## <a name="109-building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>109: построение EDMX Entity Framework с помощью Visual Studio 2013 может завершиться ошибкой MSB4062, если используются задачи EntityDeploySplit или EntityClean  
  
|||  
|-|-|  
|Подробные сведения|Инструменты MSBuild 12.0 (в составе Visual Studio 2013) изменили расположение файлов MSBuild, что привело к недействительности старых файлов целей построения Entity Framework. В результате задачи `EntityDeploySplit` и `EntityClean` завершаются ошибкой, так как они не могут найти `Microsoft.Data.Entity.Build.Tasks.dll`. Обратите внимание, что это нарушение возникает вследствие изменения набора инструментов (MSBuild и Visual Studio), а не из-за изменения платформы .NET Framework. Оно происходит только при обновлении средств разработчика, а не просто при обновлении .NET Framework.|  
|Предложение|Начиная с .NET Framework 4.6, файлы целей построения Entity Framework предназначены для работы с новым макетом MSBuild. Проблема будет решена после обновления до этой версии. Кроме того, [это](http://stackoverflow.com/a/24249247/131944) решение можно использовать для исправления файлов целей построения напрямую.|  
|Область|Значительно|  
|Версия|4.5.1-4.6|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0109|  
  
<a name="diagnostic111"></a>   
## <a name="111-xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>111: проверка схемы XSD теперь правильно обнаруживает нарушения уникальных ограничений, если используются составные ключи и один ключ пуст  
  
|||  
|-|-|  
|Подробные сведения|В версиях платформы .NET Framework, предшествовавших версии 4.6, была ошибка, из-за которой проверка XSD не могла обнаруживать уникальные ограничения по составным ключам, если один из ключей был пуст. Эта проблема решена в .NET Framework 4.6. Это приведет к выполнению более правильной проверки, но также может привести к невозможности проверки некоторого XML-кода, которая осуществлялась раньше.|  
|Предложение|Требуется проверка .NET Framework 4.0. Проверяющее приложение может быть предназначено для версии 4.5 (или более ранней) платформы .NET Framework. Однако при изменении целевой платформы на .NET 4.6 следует выполнить проверку кода, чтобы не проверять повторяющиеся составные ключи (как указано в описании этой проблемы).|  
|Область|Пограничный случай|  
|Версия|4.6|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0111|  
  
<a name="diagnostic112"></a>   
## <a name="112-calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a>112: вызов Attribute.GetCustomAttributes в свойстве индексатора больше не вызывает исключение AmbiguousMatchException, если тип индекса может разрешить неоднозначность  
  
|||  
|-|-|  
|Подробные сведения|В версиях .NET Framework, более ранних, чем 4.6, вызов `GetCustomAttribute(s)` в свойстве индексатора, которое отличалось от другого свойства только по типу индекса, приведет к `AmbiguousMatchException`. Начиная с .NET Framework 4.6, атрибуты свойства возвращаются правильно.|  
|Предложение|Имейте в виду, что теперь GetCustomAttribute(s) будут использоваться чаще. Если приложение ранее зависело от `AmbiguousMatchException`, теперь для явного поиска нескольких индексаторов следует использовать отражение.|  
|Область|Пограничный случай|  
|Версия|4.6|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName>|  
|Анализаторы|CD0112|  
  
<a name="diagnostic113"></a>   
## <a name="113-intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>113: периодически не удается выполнить прокрутку до нижнего элемента в ItemsControls (таких как ListBox и DataGrid) при использовании пользовательских DataTemplates  
  
|||  
|-|-|  
|Подробные сведения|В некоторых случаях ошибка в .NET Framework 4.5 приводит к тому, что ItemsControls (например, ListBox, ComboBox, DataGrid и т. д.) не удается выполнить прокрутку до нижнего элемента при использовании пользовательских DataTemplates. Если попытка прокрутки предпринимается повторно (после прокрутки вверх), прокрутка будет работать.|  
|Предложение|Эта проблема была устранена в .NET Framework 4.5.2 и может быть решена путем обновления до этой версии (или более поздней) платформы .NET Framework. Кроме того, пользователи по-прежнему могут перетаскивать полосы прокрутки к последним элементам в этих коллекциях, однако для успешного выполнения этой задачи это может потребоваться сделать дважды.|  
|Область|Дополнительный номер|  
|Версия|4.5-4.5.2|  
|Тип|Среда выполнения|  
|Анализаторы|CD0113|  
  
<a name="diagnostic114"></a>   
## <a name="114-glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-45"></a>114: начиная с .NET 4.5, GlyphRun.ComputeInkBoundingBox() и FormattedText.Extent возвращают разные значения  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.5 были усовершенствованы GlyphRun.ComputeInkBoundingBox() и FormattedText.Extent для решения проблем, когда в некоторых случаях в .NET Framework 4.0 прямоугольники были слишком малы для содержащихся глифов. В результате, начиная с .NET Framework 4.5, некоторые ограничивающие прямоугольники будут иметь больший размер, что приведет к незначительным отличиям в макете пользовательского интерфейса.|  
|Предложение|Имейте в виду, что размеры некоторых ограничивающих прямоугольников глифов увеличены. Эти изменения обычно улучшают представление и проверку нахождения в поле. Прежнее (до .NET 4.5) поведение можно восстановить, добавив следующую запись в файл app.config.<br /><br /> `<appsettings> <add key="IncludeAllInkInBoundingBox" value="false"> </appsettings>`|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=fullName><br /><br /> <xref:System.Windows.Media.FormattedText.Extent?displayProperty=fullName>|  
|Анализаторы|CD0114|  
  
<a name="diagnostic124"></a>   
## <a name="124-calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>124: вызов метода DataGrid.CommitEdit из обработчика CellEditEnding удаляет фокус  
  
|||  
|-|-|  
|Подробные сведения|Вызов метода DataGrid.CommitEdit из одного из обработчиков событий CellEditEnding элемента DataGrid приводит к потере фокуса DataGrid.|  
|Предложение|Это ошибка исправлена в .NET Framework 4.5.2, поэтому ее можно избежать путем обновления .NET Framework. Кроме того, ее можно избежать, явным образом повторно выбрав DataGrid после вызова CommitEdit.|  
|Область|Пограничный случай|  
|Версия|4.5-4.5.2|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName><br /><br /> <xref:System.Windows.Controls.DataGrid.CommitEdit%28System.Windows.Controls.DataGridEditingUnit%2CSystem.Boolean%29?displayProperty=fullName>|  
|Анализаторы|CD0124|  
  
<a name="diagnostic125"></a>   
## <a name="125-aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>125: ASP.NET MVC теперь экранирует пробелы в строках, переданных через параметры маршрута  
  
|||  
|-|-|  
|Подробные сведения|Чтобы соответствовать стандарту RFC 2396, пробелы в путях маршрута теперь экранируются при заполнении параметров действий из маршрута. Таким образом, в то время как `/controller/action/some data` ранее соответствовал маршруту `/controller/action/{data}` и предоставлял `some data` в качестве параметра данных, теперь он будет предоставлять `some%20data`.|  
|Предложение|Код должен быть обновлен для неэкранирования строковых параметров из маршрута. Если необходим исходный URI, доступ к нему можно получить с помощью API Request.RequestUri.OriginalString.|  
|Область|Дополнительный номер|  
|Версия|4.5.2|  
|Тип|Среда выполнения|  
|Затронутые API|[System.Web.Http.RouteAttribute](https://msdn.microsoft.com/library/system.web.http.routeattribute(v=vs.118).aspx)|  
|Анализаторы|CD0125|  
  
<a name="diagnostic127"></a>   
## <a name="127-vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>127: VB.NET больше не поддерживает частичные квалификации пространства имен для API-интерфейсов System.Windows  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET 4.5.2, в проектах VB.NET невозможно задать API-интерфейсы System.Windows с частично указанными пространствами имен. Например, ссылка на `Windows.Forms.DialogResult` завершится ошибкой. Вместо этого код должен ссылаться на полное доменное имя (`System.Windows.Forms.DialogResult`) или импортировать конкретное пространство имен и сослаться просто на `DialogResult`.|  
|Предложение|Следует обновить код для ссылки на API `System.Windows` либо с простыми именами (и импортом соответствующего пространства имен), либо с полными доменными именами.|  
|Область|Дополнительный номер|  
|Версия|4.5.2|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0127|  
  
<a name="diagnostic129"></a>   
## <a name="129-two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>129: двухсторонняя привязка данных к свойству с не предназначенным для общего доступа методом задания не поддерживается  
  
|||  
|-|-|  
|Подробные сведения|Попытка привязки данных к свойству без общедоступного метода задания никогда не поддерживалась. Начиная с .NET Framework 4.5.1, этот сценарий выдает исключение InvalidOperationException. Обратите внимание, что это новое исключение создается только для приложений, которые предназначены специально для .NET Framework 4.5.1. Если приложение предназначено для .NET Framework 4.5, вызов будет разрешен. Если приложение не предназначено для определенной версии .NET Framework, привязка будет рассматриваться как односторонняя.|  
|Предложение|Приложение следует обновить либо для использования односторонней привязки, либо для предоставления общего доступа к методу задания свойства. Кроме того, выбор .NET Framework 4.5 в качестве целевой платформы приведет к восстановлению старого поведения приложения.|  
|Область|Дополнительный номер|  
|Версия|4.5.1|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.Windows.Data.BindingMode?displayProperty=fullName>|  
|Анализаторы|CD0129|  
  
<a name="diagnostic130"></a>   
## <a name="130-marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>130: перегрузки Marshal.SizeOf и Marshal.PtrToStructure нарушают работу динамического кода  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.5.1, динамическая привязка к методам `Marshal.SizeOf` или `Marshal.PtrToStructure` (с помощью Windows PowerShell, IronPython или ключевого слова dynamic в C#) может привести к исключению `MethodInvocationExceptions`, так как были добавлены новые перегрузки этих методов, которые могут быть неоднозначными для обработчиков сценариев.|  
|Предложение|Обновите скрипты для четкого указания используемой перегрузки. Обычно нужно явным образом привести параметры типа метода как `System.Type`. Дополнительные сведения и возможные решения этой проблемы см. по [этой ссылке](https://support.microsoft.com/kb/2909958/).|  
|Область|Дополнительный номер|  
|Версия|4.5.1|  
|Тип|Среда выполнения|  
|Анализаторы|CD0130|  
  
<a name="diagnostic131"></a>   
## <a name="131-previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>131: PreviewLostKeyboardFocus вызывается повторно, если соответствующий обработчик выводит окно сообщения Windows Forms  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.5, вызов `System.Windows.Forms.MessageBox.Show` из обработчика `UIElement.PreviewLostKeyboardFocus` приведет к повторному запуску обработчика после закрытия окна сообщения. В результате может начаться бесконечный цикл вывода окон сообщений.|  
|Предложение|Существует два способа решения этой проблемы.<br /><br /> Ее можно избежать, вызвав `System.Windows.MessageBox.Show` вместо `System.Windows.Forms.MessageBox.Show`.<br /><br /> Ее можно избежать, открыв окно сообщения из обработчика событий `LostKeyboardFocus` (в отличие от обработчика событий `PreviewLostKeyboardFocus`).|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=fullName>|  
|Анализаторы|CD0131|  
  
<a name="diagnostic133"></a>   
## <a name="133-a-concurrentdictionary-serialized-in-net-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-451-or-452"></a>133: объект ConcurrentDictionary, сериализованный в .NET 4.5. с помощью NetDataContractSerializer, нельзя десериализовать в .NET 4.5.1 или 4.5.2  
  
|||  
|-|-|  
|Подробные сведения|Из-за внутренних изменений типа объекты `System.Collections.Concurrent.ConcurrentDictionary`, сериализованные в .NET Framework 4.5 с помощью `NetDataContractSerializer`, не могут быть десериализованы в .NET Framework 4.5.1 или .NET Framework 4.5.2.<br /><br /> Обратите внимание, что можно выполнять действие в другом направлении (сериализация в .NET Framework 4.5.x и десериализация в .NET Framework 4.5). Аналогичным образом, сериализация в версиях 4.x работает в .NET Framework 4.6.<br /><br /> Сериализация и десериализация в одной версии платформы .NET Framework не затрагивается.|  
|Предложение|Если необходимо сериализовать и десериализовать ConcurrentDictionary между .NET Framework 4.5 и .NET Framework 4.5.1/4.5.2, вместо NetDataContractSerializer следует использовать альтернативный сериализатор, такой как DataContractSerializer или BinaryFormatter.<br /><br /> Кроме того, поскольку эта проблема была устранена в .NET Framework 4.6, она может быть решена путем обновления до этой версии платформы .NET Framework.|  
|Область|Дополнительный номер|  
|Версия|4.5.1-4.6|  
|Тип|Среда выполнения|  
|Анализаторы|CD0133|  
  
<a name="diagnostic134"></a>   
## <a name="134-persian-calendar-now-uses-the-hijri-solar-algorithm"></a>134: теперь в персидском календаре используется алгоритм солнечного календаря хиджры  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.6, класс PersianCalendar использует алгоритм солнечного календаря хиджры. Начиная с .NET Framework 4.6, при преобразовании дат между PersianCalendar и другими календарями может быть получен немного другой результат для дат, ранее 1800 г. или позднее 2023 г. (по григорианскому календарю).<br /><br /> Кроме того, теперь `PersianCalendar.MinSupportedDateTime` имеет значение `March 22, 0622 instead of March 21, 0622`.|  
|Предложение|Имейте в виду, что при использовании персидского календаря в .NET 4.6 некоторые даты в прошлом или будущем могут несколько отличаться. Кроме того, даты, сериализуемые между процессами, которые могут выполняться в различных версиях .NET Framework, не следует хранить в виде строк дат персидского календаря (поскольку эти значения могут быть разными).|  
|Область|Дополнительный номер|  
|Версия|4.6|  
|Тип|Среда выполнения|  
|Затронутые API|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|  
|Анализаторы|CD0134|  
  
<a name="diagnostic138"></a>   
## <a name="138-calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>138: был изменен вызов метода CreateDefaultAuthorizationContext с аргументом NULL  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.6 изменилась реализация AuthorizationContext, возвращаемая вызовом `CreateDefaultAuthorizationContext(IList<IAuthorizationPolicy>)` с нулевым аргументом authorizationPolicies.|  
|Предложение|В редких случаях в приложениях WCF, которые используют настраиваемую проверку подлинности, могут возникать различия в поведении. В таких случаях прежнее поведение можно восстановить двумя способами.<br /><br /> Перекомпилируйте приложение для ориентации на версию .NET Framework, предшествующую 4.6. Для служб, размещенных в IIS, используйте элемент \<httpRuntime targetFramework="x.x" /> для выбора более ранней версии .NET Framework в качестве целевой платформы.<br /><br /> Добавьте следующую строку в раздел `<appSettings>` файла app.config: `<add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />`.|  
|Область|Дополнительный номер|  
|Версия|4.6|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29?displayProperty=fullName>|  
|Анализаторы|CD0138|  
  
<a name="diagnostic141"></a>   
## <a name="141-wpf-treeviewitem-must-be-used-within-a-treeview"></a>141: в TreeView необходимо использовать TreeViewItem WPF  
  
|||  
|-|-|  
|Подробные сведения|В версии 4.5 было представлено изменение, которое ограничивает использование элементов TreeViewItem за пределами элемента управления TreeView. Это происходит в следующих случаях.<br /><br /> Визуальный родительский элемент TreeViewItem не является панелью. (TreeViewItem, созданный для элемента управления TreeView, будет иметь панель в качестве родительского элемента.)<br /><br /> TreeViewItem является потомком VirtualizingStackPanel, выступающего в виде "узла элементов" для элемента управления "Список" (ListBox, DataGrid, ListView и т. д.). Виртуализацию включать необязательно.<br /><br /> VirtualizingStackPanel поддерживает прокрутку элементов (`ScrollUnit="Item"`).<br /><br /> Кто-то вызывает `VirtualizingStackPanel.MakeVisible(v)` для прокрутки элемента `v` в представлении. Это можно сделать явно или неявно несколькими способами. Возможно, самым распространенным способом является простой щелчок `v` для перевода в его фокуса.<br /><br /> Цепочка визуального родительского элемента от `v` к VirtualizingStackPanel проходит через TreeViewItem.<br /><br /> Другими словами, это происходит в том случае, когда TreeViewItem используется вне TreeView и пользователь щелкает потомка TreeViewItem, чтобы сделать его видимым. Проблема никогда не возникнет, если у TreeViewItem отсутствуют имеющие фокус потомки. Пример такой ситуации — TreeViewItem является корнем DataTemplate.  При возникновении этой проблемы создается исключение InvalidCastException в рамках платформы WPF.|  
|Предложение|Будет создано исправление для этой ошибки.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0141|  
  
<a name="diagnostic143"></a>   
## <a name="143-x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>143: X509CertificateClaimSet.FindClaims учитывает все аргументы claimType  
  
|||  
|-|-|  
|Подробные сведения|Если в приложениях, предназначенных для .NET Framework 4.6.1, набор утверждений X509 инициализируется из сертификата, имеющего несколько записей DNS в поле SAN, метод FindClaims пытается сопоставить аргумент claimType со всеми записями DNS.<br /><br /> В приложениях, предназначенных для предыдущих версий .NET Framework, метод FindClaims пытается сопоставить аргумент claimType только с последней записью DNS.|  
|Предложение|Это изменение затрагивает только приложения, предназначенные для .NET Framework 4.6.1. Это изменение может быть отключено (или включено, если используются версии, предшествующие 4.6.1) с помощью параметра совместимости [DisableMultipleDNSEntries](https://msdn.microsoft.com/library/mt620030%28v=vs.110%29.aspx).|  
|Область|Дополнительный номер|  
|Версия|4.6.1|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%28System.String%2CSystem.String%29?displayProperty=fullName>|  
|Анализаторы|CD0143|  
  
<a name="diagnostic144"></a>   
## <a name="144-applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>144: Application.FilterMessage больше не создает исключение для реализаций IMessageFilter.PreFilterMessage с повторным входом  
  
|||  
|-|-|  
|Подробные сведения|В версиях .NET Framework, предшествующих 4.6.1, вызов Application.FilterMessage с реализацией IMessageFilter.PreFilterMessage, которая вызывала AddMessageFilter или RemoveMessageFilter (при одновременном вызове Application.DoEvents), приведет к созданию исключения IndexOutOfRangeException.<br /><br /> Начиная с приложений, предназначенных для .NET Framework 4.6.1, это исключение больше не создается, и можно использовать фильтры с повторным входом, как описано выше.|  
|Предложение|Имейте в виду, что Application.FilterMessage больше не будет создавать исключение для описанного выше поведения IMessageFilter.PreFilterMessage с повторным входом. Будут затронуты только приложения, предназначенные для .NET Framework 4.6.1.<br /><br /> В приложениях, предназначенных для .NET Framework 4.6.1, можно отказаться от этого изменения (или в приложениях, предназначенных для более старых платформ, можно использовать изменение) с помощью параметра совместимости [DontSupportReentrantFilterMessage](https://msdn.microsoft.com/library/mt620032%28v=vs.110%29.aspx).|  
|Область|Пограничный случай|  
|Версия|4.6.1|  
|Тип|Изменение целевой платформы|  
|Затронутые API|<xref:System.Windows.Forms.Application.FilterMessage%28System.Windows.Forms.Message%40%29?displayProperty=fullName>|  
|Анализаторы|CD0144|  
  
<a name="diagnostic145"></a>   
## <a name="145-currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>145: CurrentCulture не сохраняется в операциях диспетчера WPF  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.6, изменения CurrentCulture и CurrentUICulture, внесенные в операции [диспетчеризации](https://msdn.microsoft.com/library/system.windows.threading.dispatcher%28v=vs.110%29.aspx), будут утеряны в конце операции диспетчеризации. Аналогичным образом, изменения CurrentCulture и CurrentUICulture, внесенные за пределами операции диспетчеризации, могут не отображаться при выполнении этой операции.<br /><br /> Проще говоря, это означает, что изменения CurrentCulture и CurrentUICulture могут не передаваться между обратными вызовами пользовательского интерфейса WPF и другим кодом в приложении WPF.<br /><br /> Начиная с приложений, предназначенных для .NET Framework 4.6, это происходит из-за изменения в [ExecutionContext](https://msdn.microsoft.com/library/system.threading.executioncontext%28v=vs.110%29.aspx), которое приводит к хранению CurrentCulture и CurrentUICulture в контексте выполнения. Операции диспетчеризации WPF сохраняют контекст выполнения, который используется для запуска операции и восстановления предыдущего контекста при завершении операции. Поскольку CurrentCulture и CurrentUICulture теперь являются частью этого контекста, их изменения в рамках операции диспетчеризации не сохраняются вне операции.|  
|Предложение|В приложениях, затронутых данным изменением, можно обойти эту проблему, сохранив CurrentCulture и CurrentUICulture в поле и проверив все тексты операций диспетчеризации (включая обработчики обратного вызова событий пользовательского интерфейса) на установку правильных значений CurrentCulture и CurrentUICulture. Кроме того, поскольку изменение ExecutionContext, являющееся базовым для этого изменения WPF, влияет только на приложения, предназначенные для .NET Framework 4.6 или более поздние версии, это нарушение можно исключить путем нацеливания на .NET Framework 4.5.2.|  
|Область|Дополнительный номер|  
|Версия|4.6|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0145|
