---
title: "Диагностика совместимости .NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5e481270-b62a-4cb4-8dda-5b4c5b59d61d
caps.latest.revision: 7
author: "twsouthwick"
ms.author: "tasou"
manager: "wpickett"
caps.handback.revision: 7
---
# Диагностика совместимости .NET
Диагностика совместимости .NET — анализаторов на базе Roslyn, выявления проблем совместимости между версиями .NET Framework. Этот список содержит все анализаторы доступной, несмотря на то, что только часть будет применяться к любой конкретной миграции. Анализаторы определит, какие проблемы применимы для запланированного переноса и будет всплыть только те. Для проблем разбивать затронутые версии, см. в разделе: [совместимость приложений](../../../docs/framework/migration-guide/application-compatibility.md).  
  
 Каждый выпуск включает следующие сведения:  
  
-   Описание того, что изменилось с предыдущей версии.  
  
-   Предлагается описание как изменение влияет на клиентов, а также способы обхода доступны для сохранения совместимости с версиями.  
  
-   Оценка, насколько важна изменения. Проблемы совместимости приложений делятся на следующие:  
  
    |||  
    |-|-|  
    |Значительно|Значительное изменение влияет на большое количество приложений или требует существенного изменения кода.|  
    |Дополнительный номер|Изменение влияет на небольшое количество приложений или требует незначительного изменения кода.|  
    |Пограничный случай|Изменение влияет на приложения в исключительных, нередко ситуациях.|  
    |Прозрачный|Изменение с без особого влияния на разработчика или пользователя приложения.|  
  
-   Версия указывает, когда изменение впервые появился в платформе. Некоторые изменения отменяются и также указано.  
  
-   Тип изменения:  
  
    |||  
    |-|-|  
    |Изменение целевой платформы|Изменение влияет на приложения, которые перекомпилируются для использования новой версии платформы .NET Framework.|  
    |Среда выполнения|Изменение влияет на существующие приложения, предназначенного для предыдущей версии платформы .NET Framework, но работает в более поздней версии.|  
  
-   Затронутых API, если таковые имеются.  
  
-   Идентификаторы доступных диагностики  
  
<a name="diagnostic1"></a>   
## <a name="1-soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>1: SoapFormatter не удается выполнить десериализацию хэш-таблицы и подобные упорядоченных объекты-коллекции  
  
|||  
|-|-|  
|Подробные сведения|Класс SoapFormatter не гарантирует, что объекты сериализуются в одной версии десериализации с другими версиями платформы .NET Framework. В частности некоторые упорядоченный коллекции (например, Hashtable) добавленных элементов между 4.0 и 4.5, таким образом, что объекты этих типов не удается выполнить десериализацию с платформой .NET 4.0, если бы они были serialzied с .NET 4.5. Обратите внимание, что если сериализованные данные и сериализуются и десериализуются с той же версией .NET Framework, не происходит.|  
|Предложение|Сериализация SoapFormatter необходимо заменить BinaryFormatter сериализации или NetDataContractSerialization быть устойчивым к изменениям .NET Framework.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize%28System.IO.Stream%2CSystem.Runtime.Remoting.Messaging.HeaderHandler%29?displayProperty=fullName><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%29?displayProperty=fullName><br /><br /> [SoapFormatter.Serialize (поток, объект, заголовок\<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize%28System.IO.Stream%2CSystem.Object%2CSystem.Runtime.Remoting.Messaging.Header%5B%5D%29?displayProperty=fullName>|  
|Анализаторы|CD0001B<br /><br /> CD0001A|  
  
<a name="diagnostic3"></a>   
## <a name="3-wpf-datatemplate-elements-are-now-visible-to-uia"></a>3: элементов WPF DataTemplate теперь отображаются UIA  
  
|||  
|-|-|  
|Подробные сведения|Ранее элементов DataTemplate был невидимым для автоматизации пользовательского интерфейса. Начиная с версии 4.5, обнаруживает эти элементы автоматизации пользовательского интерфейса. Это полезно во многих случаях, но может нарушить работу тестов, зависящих от UIA деревьев, не содержащая элементов DataTemplate.|  
|Предложение|Тесты Auomation пользовательский Интерфейс этого приложения может потребоваться обновление с учетом UIA дерева, включая ранее невидимые элементы DataTemplate. Например тесты, которые ожидают, что некоторые элементы рядом друг с другом теперь нужно ожидать ранее невидимые элементы UIA между ними. Или тесты, которые зависят от определенных счетчиков или индексы для UIA элементов может потребоваться обновить новыми значениями.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Windows.DataTemplate.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Windows.DataTemplate.%23ctor%28System.Object%29?displayProperty=fullName>|  
|Анализаторы|CD0003|  
  
<a name="diagnostic4"></a>   
## <a name="4-wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>4: WPF текстовое поле будет отображаться другим цветом, если текстовое поле не  
  
|||  
|-|-|  
|Подробные сведения|В .NET 4.5, если элемент управления текстовым окном WPF неактивно (фокус не установлен), выбранный текст внутри поля будут отображаться другим цветом, чем когда элемент управления является активным.|  
|Предложение|Прежнее поведение (.NET 4.0) могут быть восстановлены, задав [FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported](https://msdn.microsoft.com/en-us/library/system.windows.frameworkcompatibilitypreferences.areinactiveselectionhighlightbrushkeyssupported\(v=vs.110\).aspx) значение false.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|Анализаторы|CD0004|  
  
<a name="diagnostic5"></a>   
## <a name="5-listtforeach-can-throw-exception-when-modifying-list-item"></a>5: List<>\>. По каждому элементу может вызвать исключение при изменении элемента списка  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET 4.5 `List<T>.ForEach` перечислитель вызовет исключение InvalidOperationException при изменении элемента в коллекции вызывающего. Ранее это не вызовет исключение, но может привести к конкуренции.|  
|Предложение|В идеальном случае код должен быть решен не следует изменять списки при перечислении их элементов, поскольку это никогда не безопасной работы. Чтобы вернуться к предыдущему поведению, однако приложение предназначено для платформы .NET 4.0.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.Collections.Generic.List%601.ForEach%28System.Action%7B%600%7D%29?displayProperty=fullName>|  
|Анализаторы|CD0005|  
  
<a name="diagnostic6"></a>   
## <a name="6-systemuri-parsing-adheres-to-rfc-3987"></a>6: синтаксический анализ System.Uri придерживается RFC 3987  
  
|||  
|-|-|  
|Подробные сведения|Синтаксический анализ URI был изменен несколькими способами в .NET 4.5. Обратите внимание, что эти изменения касаются только кода, предназначенного для .NET 4.5. Если двоичный нацелен на .NET 4.0, будет наблюдаться старого поведения. Внесены следующие изменения в синтаксическом анализе URI в .NET 4.5.<br /><br /> Выполняет синтаксический анализ URI нормализация и проверка в соответствии с последними правилами IRI в стандарте RFC 3987 символов<br /><br /> Форма нормализации Юникода C будет выполняться только на часть URI узла<br /><br /> Недопустимый mailto: идентификаторы URI теперь будет вызывать исключение<br /><br /> Теперь сохраняются конечные точки в конце сегмента пути<br /><br /> `file://`Идентификаторы URI не теряется `?` символ<br /><br /> Управляющие символы Юникода `U+0080` через `U+009F` не поддерживаются<br /><br /> Символ запятой `,` или `%2c` не отменяются автоматически|  
|Предложение|При необходимости (они часто не) старого семантику синтаксического анализа .NET 4.0 URI, они могут использоваться, предназначенные для .NET 4.0. Это можно сделать с помощью TargetFrameworkAttribute на сборку или с помощью пользовательского интерфейса системы проектов Visual Studio на странице «свойства проекта».|  
|Область|Значительно|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.Uri.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29?displayProperty=fullName><br /><br /> <xref:System.Uri.%23ctor%28System.Uri%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.String%2CSystem.UriKind%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.String%2CSystem.Uri%40%29?displayProperty=fullName><br /><br /> <xref:System.Uri.TryCreate%28System.Uri%2CSystem.Uri%2CSystem.Uri%40%29?displayProperty=fullName>|  
|Анализаторы|CD0006D<br /><br /> CD0006C<br /><br /> CD0006F<br /><br /> CD0006E<br /><br /> CD0006A<br /><br /> CD0006G<br /><br /> CD0006B|  
  
<a name="diagnostic10"></a>   
## <a name="10-systemuri-escaping-now-supports-rfc-3986-httptoolsietforghtmlrfc3986"></a>10: экранирование System.Uri теперь поддерживает RFC 3986 (http://tools.ietf.org/html/rfc3986)  
  
|||  
|-|-|  
|Подробные сведения|Экранирование URI изменилось в .NET 4.5 для поддержки [RFC 3986](http://tools.ietf.org/html/rfc3986). Конкретные изменения включают:<br /><br /> Метод `EscapeDataString` преобразует в escape-последовательность зарезервированные символы в соответствии с RFC 3986.<br /><br /> Метод `EscapeUriString` не преобразует в escape-последовательность зарезервированные символы.<br /><br /> Метод `UnescapeDataString` не создает исключение, если ему встречается неверная escape-последовательность.<br /><br /> Преобразование незарезервированных символов в escape-символы отменяется.|  
|Предложение|Обновления приложений не полагаться на UnescapeDataString исключение в случае Недопустимая escape-последовательность. Такой последовательности должны обнаруживаться прямо сейчас.<br /><br /> Аналогичным образом ожидается, что Escaped и escape-последовательность URI и строки данных могут отличаться от .NET 4.0 и .NET 4.5 и не следует сравнивать версиях .NET напрямую. Вместо этого они должны анализируется и нормализации в одной версии платформы .NET, перед выполнением каких-либо сравнений.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Uri.EscapeDataString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.EscapeUriString%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Uri.UnescapeDataString%28System.String%29?displayProperty=fullName>|  
|Анализаторы|CD0010A<br /><br /> CD0010B<br /><br /> CD0010C|  
  
<a name="diagnostic11"></a>   
## <a name="11-systemnetpeertopeercollaboration-unavailable-on-windows-8"></a>11: System.Net.PeerToPeer.Collaboration, недоступные в Windows 8  
  
|||  
|-|-|  
|Подробные сведения|Пространство имен System.Net.PeerToPeer.Collaboration недоступна в Windows 8 или более поздней.|  
|Предложение|Приложения, которые поддерживают Windows 8 или выше, должны быть обновлены не зависят от этого пространства имен или его элементов.|  
|Область|Значительно|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName>|  
|Анализаторы|CD0011|  
  
<a name="diagnostic12"></a>   
## <a name="12-mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>12: каталоги MEF реализуют интерфейс IEnumerable и таким образом, больше не может использоваться для создания сериализатора  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.5, каталоги MEF реализуют интерфейс IEnumerable и таким образом, больше не может использоваться для создания сериализатора (объекта XmlSerializer). При попытке сериализации каталога MEF происходит вызов исключения.|  
|Предложение|Больше не использовать MEF для создания сериализатора|  
|Область|Значительно|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0012|  
  
<a name="diagnostic13"></a>   
## <a name="13-missing-target-framework-moniker-results-in-40-behavior"></a>13: отсутствует моникер целевой платформы приводит к поведению версии 4.0  
  
|||  
|-|-|  
|Подробные сведения|Приложения без [TargetFrameworkAttribute](https://msdn.microsoft.com/en-us/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) применяется на уровне будут сборки автоматически запускается с использованием семантики (совместимости) платформы .NET Framework 4.0. Для обеспечения высокого качества, рекомендуется явно объяснить все двоичные файлы с TargetFrameworkAttribute указывает версию платформы .NET Framework, они были созданы. Обратите внимание, что с помощью моникера целевой платформы в файле проекта будет caues MSBuild для автоматического применения TargetFrameworkAttribute.|  
|Предложение|Объект [атрибут target framework](https://msdn.microsoft.com/en-us/library/system.runtime.versioning.targetframeworkattribute\(v=vs.110\).aspx) должен быть получен, либо посредством добавления атрибута непосредственно для сборки или путем указания целевой платформы в [файл проекта или с помощью Visual Studio проекта свойства графического интерфейса](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx).|  
|Область|Значительно|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0013|  
  
<a name="diagnostic14"></a>   
## <a name="14-no-longer-able-to-set-enableviewstatemac-to-false"></a>14: больше не может установить EnableViewStateMac значение false  
  
|||  
|-|-|  
|Подробные сведения|ASP.NET теперь не позволяет разработчикам указывать `<pages enableViewStateMac="false"/>` или `<@Page EnableViewStateMac="false" %>`. Код проверки подлинности сообщения (MAC) состояния просмотра теперь принудительно применяется для всех запросов со встроенным состоянием просмотра. Затрагиваются только приложения, которые явно EnableViewStateMac свойству присвоено значение false.|  
|Предложение|EnableViewStateMac должно присваиваться значение true, и список ошибок MAC должны быть устранены (как описано в [это](https://support.microsoft.com/en-us/kb/2915218) руководство, в котором содержится несколько решений в зависимости от причины ошибки MAC).|  
|Область|Значительно|  
|Версия|4.5.2|  
|Тип|Среда выполнения|  
|Анализаторы|CD0014|  
  
<a name="diagnostic18"></a>   
## <a name="18-blockingcollectionttrytakefromany-does-not-throw-anymore"></a>18: BlockingCollection<>\>. TryTakeFromAny больше не вызывает  
  
|||  
|-|-|  
|Подробные сведения|Если один из входных коллекций помечена как завершенная, `BlockingCollection<T>.TryTakeFromAny(BlockingCollection<T>[], T)` больше не возвращает значение -1 и `BlockingCollection<T>.TakeFromAny` больше не вызывает исключение. Это изменение позволяет работать с коллекциями, если одна из коллекций пуста или завершена, но другая коллекция по-прежнему содержит элементы, которые можно извлечь.|  
|Предложение|Если возвращается значение -1 и генерации TakeFromAny TryTakeFromAny случаев заблокированной коллекции выполняются в целях управления потоком, такой код теперь можно изменить для использования `.Any(b => b.IsCompleted)` для обнаружения этого условия.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|[BlockingCollection<>\>. TakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>. TakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>. TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>. TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.Int32%29?displayProperty=fullName><br /><br /> [BlockingCollection<>\>. TryTakeFromAny (BlockingCollection<>\>\<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|Анализаторы|CD0018A<br /><br /> CD0018B|  
  
<a name="diagnostic19"></a>   
## <a name="19-xmlschemaexception-now-sets-line-positions-properly"></a>19: XmlSchemaException теперь наборов строк позиций должным образом  
  
|||  
|-|-|  
|Подробные сведения|Если возникает ошибка проверки LoadOptions.SetLineInfo значение передается методу Load, свойства XmlSchemaException.LineNumber и XmlSchemaException.LinePosition теперь содержат сведения о строке.|  
|Предложение|Код обработки исключений, который предполагается XmlSchemaException.LineNumber и XmlSchemaException.LinePosition не будет необходимо обновить набор, поскольку эти свойства теперь устанавливается правильно при использовании SetLineInfo при загрузке XML.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Xml.Linq.LoadOptions?displayProperty=fullName>|  
|Анализаторы|CD0019|  
  
<a name="diagnostic20"></a>   
## <a name="20-systemactivities-is-now-aptca"></a>20: System.Activities теперь является атрибутом APTCA  
  
|||  
|-|-|  
|Подробные сведения|Сборка помечена атрибутом AllowPartiallyTrustedCallersAttribute.|  
|Предложение|Производные классы не может быть помечены атрибутом SecurityCriticalAttribute. Ранее производные типы должны были быть помечены атрибутом SecurityCriticalAttribute. Однако это изменение не должно иметь никаких реальных последствий.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0020|  
  
<a name="diagnostic21"></a>   
## <a name="21-workflow-30-types-are-obsolete"></a>21: типы рабочих процессов 3.0 устарели  
  
|||  
|-|-|  
|Подробные сведения|API-интерфейсы Windows Workflow Foundation (WWF) 3.0 (которые из пространства имен System.Workflow) теперь являются устаревшими.|  
|Предложение|Вместо этого следует использовать новые интерфейсы API WWF 4.0 (в System.Activities). Пример использования новых интерфейсов API можно найти [здесь](https://msdn.microsoft.com/en-us/library/jj205427.aspx) и дальнейшей руководство доступно [здесь](http://blogs.msdn.com/b/workflowteam/archive/2012/02/08/deprecatingwf3.aspx). Кроме того поскольку API-интерфейсы WWF 3.0 по-прежнему поддерживаются, их можно использовать и предупреждение во время построения избегать подавление его или с помощью более старой версией компилятора.|  
|Область|Значительно|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0021|  
  
<a name="diagnostic22"></a>   
## <a name="22-some-workflow-drag-and-drop-apis-are-obsolete"></a>22: некоторые рабочий процесс перетаскивания API-интерфейсы являются устаревшими  
  
|||  
|-|-|  
|Подробные сведения|Этот API перетаскивание рабочего процесса является устаревшим и будут отображаться предупреждения компилятора, если приложение будет перестроен с 4.5.|  
|Предложение|Новые [DragDropHelper](https://msdn.microsoft.com/en-us/library/system.activities.presentation.dragdrophelper\(v=vs.110\).aspx) следует использовать интерфейсы API, которые поддерживают операции с несколькими объектами. Кроме того можно подавить предупреждения построения или их можно избежать с помощью более старой версией компилятора. Интерфейсы API по-прежнему поддерживаются.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem%28System.Windows.DragEventArgs%29?displayProperty=fullName><br /><br /> <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29?displayProperty=fullName>|  
|Анализаторы|CD0022|  
  
<a name="diagnostic23"></a>   
## <a name="23-new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a>23: новые перегрузки (неоднозначных) Dispatcher.Invoke может привести к другому  
  
|||  
|-|-|  
|Подробные сведения|.NET Framework 4.5 добавляет новые перегрузки, включающие параметр типа System.Action Dispatcher.Invoke. Если существующий код перекомпилируется, компиляторы могут разрешить вызовы методов Dispatcher.Invoke, имеющие параметр делегата, как вызовы методов Dispatcher.Invoke с параметром System.Action. Если вызов перегрузки Dispatcher.Invoke с параметром делегатом разрешается как вызов перегрузки Dispatcher.Invoke с параметром System.Action, могут возникнуть следующие различия в поведении:<br /><br /> При возникновении исключения, Dispatcher.UnhandledExceptionFilter и Dispatcher.UnhandledException события не вызываются. Вместо этого исключения обрабатываются событием UnobservedTaskException.<br /><br /> Вызовы некоторых членов, таких как DispatcherOperation.Result, блокируются до завершения операции.|  
|Предложение|Избежать неоднозначности (и потенциальные различия в исключений, обработки или блокирование поведения), код, вызывающий Dispatcher.Invoke можно передать пустой object [] как второй параметр вызова необходимо убедиться, что для разрешения перегрузки метода .NET 4.0.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Такие API|[Dispatcher.Invoke (делегат, объект\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (объект делегата TimeSpan,\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (объекта делегата, TimeSpan, DispatcherPriority,\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.TimeSpan%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [Dispatcher.Invoke (объект делегата, DispatcherPriority,\<xref:System.Windows.Threading.Dispatcher.Invoke%28System.Delegate%2CSystem.Windows.Threading.DispatcherPriority%2CSystem.Object%5B%5D%29?displayProperty=fullName>|  
|Анализаторы|CD0023|  
  
<a name="diagnostic24"></a>   
## <a name="24-encoderparameter-ctor-is-obsolete"></a>24: EncoderParameter конструктор устарел.  
  
|||  
|-|-|  
|Подробные сведения|`EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` Конструктор является устаревшим и будет представлена предупреждения построения, если используется.|  
|Предложение|Хотя `EncoderParameter.EncoderParameter(Encoder, Int32, Int32, Int32)` конструктор будет продолжать работать, следующий конструктор следует использовать во избежание предупреждение устаревшие построения при повторной компиляции кода с помощью средств .NET 4.5: [EncoderParameter.EncoderParameter (кодировщик, Int32, EncoderParameterValueType, IntPtr)](https://msdn.microsoft.com/en-us/library/hh875096\(v=vs.110\).aspx).|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|Анализаторы|CD0024|  
  
<a name="diagnostic26"></a>   
## <a name="26-change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>26: изменение в поведении для Task.WaitAll методы с аргументами времени ожидания  
  
|||  
|-|-|  
|Подробные сведения|Поведение Task.WaitAll было внесено более согласованной в .NET 4.5.<br /><br /> В .NET Framework 4 поведение этих методов было непоследовательным. Если одна или несколько задач были завершены или отменены до вызова метода по истечении времени ожидания метод вызвал исключение AggregateException. Если никакие задачи не была завершена или отменена до вызова метода, но одна или несколько задач входили в эти состояния после вызова метода по истечении времени ожидания метод возвратил значение false.<br />В .NET Framework 4.5 эти перегрузки метода теперь возвращают значение false, если все задачи по-прежнему выполняются после истечения интервала времени ожидания, и вызывают исключение AggregateException только в том случае, если входная задача была отменена (независимо от того, была ли она до или после вызова метода), и никакие другие задачи по-прежнему работают.|  
|Предложение|Если AggregateException перехвачено с точки зрения обнаружение задачу, которая была отменена до вызова метода WaitAll вызываемого кода вместо этого делать же обнаружения через свойство IsCanceled (например:. Любой (t => t.IsCanceled)), так как .NET 4.6 только создаст исключение в этом случае, если выполняются все ожидаемая задачи до времени ожидания.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|[Task.WaitAll (задача\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%29?displayProperty=fullName><br /><br /> [Task.WaitAll (задача\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.Int32%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> [Task.WaitAll (задача\<xref:System.Threading.Tasks.Task.WaitAll%28System.Threading.Tasks.Task%5B%5D%2CSystem.TimeSpan%29?displayProperty=fullName>|  
|Анализаторы|CD0026|  
  
<a name="diagnostic27"></a>   
## <a name="27-change-in-behavior-in-data-definition-language-ddl-apis"></a>27: изменение в поведении в определения языка данных (DDL) API-интерфейсов  
  
|||  
|-|-|  
|Подробные сведения|Поведение API-интерфейсы DDL при указании AttachDBFilename изменилось следующим образом:<br /><br /> Строки подключения не требуется указывать значение исходного каталога. Ранее требовались AttatchDBFilename и исходный каталог.<br /><br /> Если указаны AttatchDBFilename и начальный каталог и данный MDF-файл существует, метод ObjectContext.DatabaseExists возвращает значение true. Ранее возвращается значение false.<br /><br /> Если указаны AttatchDBFilename и начальный каталог и данный MDF-файл существует, вызывая метод ObjectContext.DeleteDatabase удаляет файлы.<br /><br /> Если ObjectContext.DeleteDatabase вызывается в том случае, когда в строке подключения указано значение AttachDBFilename с несуществующим MDF-ФАЙЛОМ и исходный каталог, который не существует, метод вызывает исключение InvalidOperationException. Раньше он вызывал исключение SqlException.|  
|Предложение|Эти изменения облегчают создание средств и приложений, в которых используются API-интерфейсы DDL. Эти изменения могут повлиять на совместимость приложений в следующих сценариях:<br /><br /> Пользователь пишет код, который выполняет команду DROP DATABASE напрямую, а не вызывающего ObjectContext.DeleteDatabase возвращает значение true, если ObjectContext.DatabaseExists. Это нарушает логику существующего кода, если база данных не присоединена, но MDF-файл существует.<br /><br /> Пользователь пишет код, который ожидает ObjectContext.DeleteDatabase метод вызывает исключение SqlException, а не исключение InvalidOperationException, когда исходный каталог- и MDF-файл не существуют.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0027|  
  
<a name="diagnostic28"></a>   
## <a name="28-machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>28: методы MachineKey.Encode и MachineKey.Decode устарели  
  
|||  
|-|-|  
|Подробные сведения|В настоящее время эти методы считаются устаревшими. При компиляции кода, который вызывает эти методы, создается предупреждение компилятора.|  
|Предложение|Взамен рекомендуется использовать [MachineKey.Protect](https://msdn.microsoft.com/en-us/library/system.web.security.machinekey.protect\(v=vs.110\).aspx) и [MachineKey.Unprotect](https://msdn.microsoft.com/en-us/library/system.web.security.machinekey.unprotect\(v=vs.110\).aspx). Кроме того можно подавить предупреждения построения или их можно избежать с помощью более старой версией компилятора. Интерфейсы API по-прежнему поддерживаются.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.Web.Security.MachineKey.Decode%28System.String%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName><br /><br /> [MachineKey.Encode (Byte\<xref:System.Web.Security.MachineKey.Encode%28System.Byte%5B%5D%2CSystem.Web.Security.MachineKeyProtection%29?displayProperty=fullName>|  
|Анализаторы|CD0028|  
  
<a name="diagnostic29"></a>   
## <a name="29-the-replace-method-in-odata-urls-is-disabled-by-default"></a>29: метод Replace в URL-адресах OData по умолчанию отключена  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.5, метод Replace в URL-адресах OData по умолчанию отключены. Если заменить OData отключен (по умолчанию), все запросы пользователя, включая функции replace (которые используются редко) завершатся ошибкой.|  
|Предложение|Если необходим метод replace (используется редко), его можно включить через [параметры конфигурации](https://msdn.microsoft.com/en-us/library/system.data.services.configuration.dataservicesfeaturessection.replacefunction.aspx). Тем не менее метод включен замены можно открывать уязвимости системы безопасности и должен использоваться только после тщательной проверки.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Data.Services.DataService%601?displayProperty=fullName>|  
|Анализаторы|CD0029|  
  
<a name="diagnostic30"></a>   
## <a name="30-systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a>30: System.ServiceModel.Web.WebServiceHost объект больше не добавляет конечную точку по умолчанию  
  
|||  
|-|-|  
|Подробные сведения|System.ServiceModel.Web.WebServiceHost объект больше не добавляет конечную точку по умолчанию, если кодом приложения была добавлена явная конечная точка.|  
|Предложение|Если пользователи хотят иметь возможность подключаться к конечной точке по умолчанию и других явные конечные точки были добавлены WebServiceHost, конечные точки по умолчанию необходимо также добавить явным образом (с помощью AddDefaultEndpoints).|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.ServiceModel.Description.ServiceEndpoint%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%29?displayProperty=fullName><br /><br /> <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint%28System.String%2CSystem.ServiceModel.Channels.Binding%2CSystem.Uri%2CSystem.Uri%29?displayProperty=fullName>|  
|Анализаторы|CD0030A<br /><br /> CD0030B|  
  
<a name="diagnostic31"></a>   
## <a name="31-eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>31: EventSource.WriteEvent impls необходимо передать WriteEvent те же параметры, полученных (а также идентификатор)  
  
|||  
|-|-|  
|Подробные сведения|Среда выполнения теперь реализуется контракт, задающий следующее: класс, производный от EventSource, определяющий метод событий ETW должен вызвать базовый класс метода EventSource.WriteEvent с Идентификатором события, а затем те же аргументы, которые был передан метод событий ETW.|  
|Предложение|IndexOutOfRangeException исключение в том случае, если прослушивателя событий считывает EventSource данные в процессе для источника события, нарушающего контракт.|  
|Область|Дополнительный номер|  
|Версия|4.5.1|  
|Тип|Среда выполнения|  
|Анализаторы|CD0031|  
  
<a name="diagnostic32"></a>   
## <a name="32-minfreememorypercentagetoactiveservice-is-now-respected"></a>32: теперь учитывается MinFreeMemoryPercentageToActiveService  
  
|||  
|-|-|  
|Подробные сведения|Этот параметр задает минимальный объем памяти, который должен быть доступен на сервере перед активацией службы WCF. Он предназначен для предотвращения исключения OutOfMemoryException. В .NET Framework 4.5 этот параметр не оказывает никакого влияния. Параметр используется в .NET Framework 4.5.1.|  
|Предложение|Исключение возникает, если объем свободной памяти на веб-сервере меньше процентного значения, заданного параметром конфигурации. Некоторые службы WCF, которые успешно запускались и выполнялись в условиях ограниченной памяти, теперь могут завершаться ошибкой.|  
|Область|Дополнительный номер|  
|Версия|4.5.1|  
|Тип|Среда выполнения|  
|Анализаторы|CD0032|  
  
<a name="diagnostic33"></a>   
## <a name="33-xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>33: развертывание сущностей XmlTextReader DTD не более 10 000 000 символов.  
  
|||  
|-|-|  
|Подробные сведения|Развертывание сущностей DTD не теперь более 10 000 000 символов. Загрузка XML-файлов без развертывания сущностей DTD или с ограниченным развертыванием сущностей DTD не изменяется. Файлы с сущностями DTD, которые развертываются до более чем 10 000 000 символов, не загружаются и теперь вызывают исключение.|  
|Предложение|Если ограничение развертывания сущностей DTD равно 10 000 000 слишком мало, значение может быть переопределен с [XmlReaderSettings.MaxCharactersFromEntities](https://msdn.microsoft.com/en-us/library/system.xml.xmlreadersettings.maxcharactersfromentities%28v=vs.110%29.aspx) свойство. Может быть передан с правильное значение MaxCharactersFromEntity XmlReaderSettings [XmlReader.Create](https://msdn.microsoft.com/en-us/library/System.Xml.XmlReader.Create\(v=vs.110\).aspx)|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Xml.XmlTextReader.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.Stream%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.Stream%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.IO.TextReader%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.String%2CSystem.Xml.XmlNodeType%2CSystem.Xml.XmlParserContext%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader.%23ctor%28System.Xml.XmlNameTable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.XmlTextReader?displayProperty=fullName>|  
|Анализаторы|CD0033|  
  
<a name="diagnostic35"></a>   
## <a name="35-xslt-style-sheet-exception-message-changed"></a>35: изменить сообщение об исключении таблицы стилей XSLT  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.5 текст сообщения об ошибке, когда XSLT-файл слишком сложный является «стилей слишком сложен.» В предыдущих версиях сообщение об ошибке имело вид "Ошибка компиляции XSLT". Код приложений, который зависит от текста сообщения об ошибке, больше не будет работать. Однако типы исключений остаются теми же, поэтому это изменение не должно иметь никаких реальных последствий.|  
|Предложение|Обновить код приложения, в зависимости от excepton сообщение из этой ошибки следует ожидать новых сообщений или обновите код, чтобы зависеть только от типа исключения (даже лучше) ([XsltException](https://msdn.microsoft.com/en-us/library/system.xml.xsl.xsltexception\(v=vs.110\).aspx)), который не был изменен.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|[XslCompiledTransform.Load (MethodInfo, байтов\[\], тип\<xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Reflection.MethodInfo%2CSystem.Byte%5B%5D%2CSystem.Type%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.String%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XPath.IXPathNavigable%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Xml.XmlReader%2CSystem.Xml.Xsl.XsltSettings%2CSystem.Xml.XmlResolver%29?displayProperty=fullName>|  
|Анализаторы|CD0035|  
  
<a name="diagnostic36"></a>   
## <a name="36-wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>36: WF сериализует Expressions.Literal<> \</> \> даты по-разному теперь (разбивает пользовательские средства синтаксического анализа XAML)  
  
|||  
|-|-|  
|Подробные сведения|Связанный [ValueSerializer](https://msdn.microsoft.com/en-us/library/system.windows.markup.valueserializer\(v=vs.110\).aspx) объекта будет преобразовывать DateTime или DateTimeOffset, секунды и миллисекунды компоненты которого не равны нулю и (для DateTime значений), свойство DateTime.Kind не определено в синтаксис элемента свойства вместо строки. Это изменение позволяет значения DateTime и DateTimeOffset и обратно. Пользовательские средства синтаксического анализа XAML, в которых предполагается, что входные данные XAML имеют синтаксис атрибутов, не будут работать правильно.|  
|Предложение|Это изменение позволяет значения DateTime и DateTimeOffset и обратно. Пользовательские средства синтаксического анализа XAML, в которых предполагается, что входные данные XAML имеют синтаксис атрибутов, не будут работать правильно.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0036|  
  
<a name="diagnostic37"></a>   
## <a name="37-new-enum-values-in-wpfs-pagerangeselection"></a>37: новые значения перечисления в WPF PageRangeSelection  
  
|||  
|-|-|  
|Подробные сведения|Были добавлены два новых члена (CurrentPage и SelectedPage) [PageRangeSelection](https://msdn.microsoft.com/en-us/library/system.windows.controls.pagerangeselection\(v=vs.110\).aspx) перечисления.|  
|Предложение|В большинстве случаев эти изменения не влияют на код пользователя. Код, зависящий от конкретного число элементов, существующих в Enum.GetNames или Enum.GetValues вызывает PageRangeSelection, следует изменить тип, но.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>|  
|Анализаторы|CD0037|  
  
<a name="diagnostic38"></a>   
## <a name="38-wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>38: WPF DispatcherSynchronizationContext.CreateCopy теперь возвращает новую копию вместо текущего экземпляра  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4 DispatcherSynchronizationContext.CreateCopy() возвращает ссылку на текущий экземпляр в основном в качестве оптимизации производительности. В .NET Framework 4.5 он возвращает новый экземпляр, что делает возможным в первый раз заключить, что равно ссылки указывают на то, что выполняющий поток находится в контексте правильная синхронизация.  Это маловероятно, что повлияет на код, который проверяет подлинность эти ссылки, но из-за изменения, необходимо протестировать код, который вызывает DispatcherSynchronizationContext.CreateCopy в ходе миграции на .NET Framework 4.5 или более поздней версии.|  
|Предложение|Имейте в виду, что DispatcherSynchronizationContext.CreateCopy() теперь возвращают новый объект SynchronizationContext.  Ранее код, который используется эквивалентности ссылок, созданный таким способом, не был проверяется на самом деле, ли он в правильном контексте, но не при построении от .NET 4.5 или более поздней версии.  Хотя маловероятно, что вызывает серьезные проблемы, проверяя пути уязвимого кода должно быть достаточно для определения, если это создает проблемы.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=fullName>|  
|Анализаторы|CD0038|  
  
<a name="diagnostic39"></a>   
## <a name="39-systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>39: System.Threading.Tasks.Task больше не вызывают ObjectDisposedException после удаления объекта  
  
|||  
|-|-|  
|Подробные сведения|За исключением Task.IAsyncResult.AsyncWaitHandle System.Threading.Tasks.Task методы больше не вызывают исключение ObjectDisposedException после удаления объекта.<br />Это изменение обеспечивает возможность использования кэшированных задач. Например, метод может возвратить кэшированную задачу для представления уже выполненной операции вместо выделения новой задачи. В предыдущих версиях платформы .NET Framework это было невозможно, поскольку любой потребитель задачи мог удалить ее, что делало ее непригодной для использования.|  
|Предложение|Имейте в виду, что задача методы могут не вызывать ObjectDisposedExceptions в случаях при уничтожении объекта. Если приложение было в зависимости от это исключение, чтобы знать, что задача был удален, его необходимо обновить явно проверить состояние задачи с помощью [Task.Status](https://msdn.microsoft.com/en-us/library/system.threading.tasks.task.status\(v=vs.110\).aspx).|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0039|  
  
<a name="diagnostic40"></a>   
## <a name="40-different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>40: обработка для методов ObjectContext.CreateDatabase и DbProviderServices.CreateDatabase различных исключений  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET 4.5, если происходит сбой создания базы данных, `CreateDatabase` методов будет произведена попытка удалить пустую базу данных. Если эта операция пройдет успешно, исходное `SQLException` будут распространяться (вместо `InvalidOperationException` , всегда было создано в .NET 4.0)|  
|Предложение|При перехвате исключения InvalidOperationException при выполнении ObjectContext.CreateDatabase или DbProviderServices.CreateDatabase, SQLExceptions должны теперь также можно перехватить.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Data.Common.DbProviderServices.CreateDatabase%28System.Data.Common.DbConnection%2CSystem.Nullable%7BSystem.Int32%7D%2CSystem.Data.Metadata.Edm.StoreItemCollection%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|Анализаторы|CD0040|  
  
<a name="diagnostic41"></a>   
## <a name="41-objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>41: ObjectContext.Translate и ObjectContext.ExecuteStoreQuery теперь поддерживают тип перечисления  
  
|||  
|-|-|  
|Подробные сведения|В .NET 4.0, общий параметр `T` из `ObjectContext.Translate` и `ObjectContext.ExecuteStoreQuery` не удалось найти методы перечисления. Теперь этот сценарий поддерживается.|  
|Предложение|Если перевод или ExecuteStoreQuery был вызван для типа enum в .NET 4.0, "0" был возвращен. Если такое поведение нежелательно, следует заменить вызовы на константы 0 (или его эквивалент перечисления).|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|[ObjectContext.ExecuteStoreQuery<>\>(строка, объект\<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> [ObjectContext.ExecuteStoreQuery<>\>(объект String, String, MergeOption,\<xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601%28System.String%2CSystem.String%2CSystem.Data.Objects.MergeOption%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%29?displayProperty=fullName><br /><br /> <xref:System.Data.Objects.ObjectContext.Translate%60%601%28System.Data.Common.DbDataReader%2CSystem.String%2CSystem.Data.Objects.MergeOption%29?displayProperty=fullName>|  
|Анализаторы|CD0041|  
  
<a name="diagnostic42"></a>   
## <a name="42-enumerableemptytresult-always-returns-cached-instance"></a>42: Enumerable.Empty служит<> \</> \> всегда возвращает кэшированное экземпляра  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET 4.5, `Enumerable.Empty` всегда возвращает кэшированный внутренний экземпляр `IEnumerable<T>`.<br /><br /> Ранее `Enumerable.Empty` будет кэшировать пустой `IEnumerable<T>` в момент вызова API, что означает, что в некоторых ситуациях, в котором `Enumerable.Empty` был вызван быстро и параллельно, разные экземпляры типа могут быть возвращены для различных вызовов API.|  
|Предложение|Из-за прежнее поведение является недетерминированным, код вряд ли зависимые от нее. Тем не менее, в том маловероятном случае, пустая перечисляемых коллекциях сравниваются и иногда считаются неравными, следует создать явную пустые массивы (`new T[0]`) вместо `Enumerable.Empty`.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=fullName>|  
|Анализаторы|CD0042|  
  
<a name="diagnostic43"></a>   
## <a name="43-httprequestcontentencoding-property-prohibits-utf7"></a>43: свойство HttpRequest.ContentEncoding запрещает UTF7  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.5, кодировка UTF-7 запрещена в теле HttpRequests. Данные для приложений, которые зависят от поступающих данных UTF-7, в некоторых случаях декодируются неверно.|  
|Предложение|В идеальном случае приложения должны обновляться не использовать кодировку UTF-7 в HttpRequests. Кроме того, можно восстановить устаревшее поведение с помощью `aspnet:AllowUtf7RequestContentEncoding` атрибут [appSettings](https://msdn.microsoft.com/en-us/library/hh975440\(v=vs.110\).aspx) элемента.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=fullName>|  
|Анализаторы|CD0043|  
  
<a name="diagnostic44"></a>   
## <a name="44-httputilityjavascriptstringencode-escapes-ampersand"></a>44: HttpUtility.JavaScriptStringEncode экранирует амперсанд  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.5, JavaScriptStringEncode экранирует символ амперсанда (&).|  
|Предложение|Если приложение зависит от предыдущего поведения этот метод, можно добавить параметр aspnet:JavaScriptDoNotEncodeAmpersand [элемент appSettings ASP.NET](https://msdn.microsoft.com/en-us/library/hh975440\(v=vs.110\).aspx) в файле конфигурации.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.HttpUtility.JavaScriptStringEncode%28System.String%2CSystem.Boolean%29?displayProperty=fullName>|  
|Анализаторы|CD0044A<br /><br /> CD0044B|  
  
<a name="diagnostic46"></a>   
## <a name="46-eventlistener-truncates-strings-with-embedded-nulls"></a>46: EventListener усекает строки с внедренными значениями NULL  
  
|||  
|-|-|  
|Подробные сведения|EventListener усекает строки с внедренными значениями NULL. Символы NULL не поддерживаются с помощью класса EventSource. Изменение влияет только на приложения, использующие EventListener для чтения данных EventSource в процессе и символы null, используйте в качестве разделителей.|  
|Предложение|EventSource данные должны обновляться, если это возможно, чтобы не использовать внедренные символы null.|  
|Область|Пограничный случай|  
|Версия|4.5.1|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%2CSystem.Diagnostics.Tracing.EventKeywords%2CSystem.Collections.Generic.IDictionary%7BSystem.String%2CSystem.String%7D%29?displayProperty=fullName> \</String, String>|  
|Анализаторы|CD0046|  
  
<a name="diagnostic48"></a>   
## <a name="48-obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>48: экспортирует ObsoleteAttribute как ObsoleteAttribute и DeprecatedAttribute в сценариях WinMD  
  
|||  
|-|-|  
|Подробные сведения|При создании библиотеки метаданных Windows (winmd-файл), атрибут ObsoleteAttribute экспортируется как ObsoleteAttribute и Windows.Foundation.DeprecatedAttribute.|  
|Предложение|Перекомпиляции существующего исходного кода, который использует атрибут ObsoleteAttribute могут выдаваться предупреждения при использовании кода из C + +/ CX или JavaScript.<br /><br /> Не рекомендуется применение ObsoleteAttribute и Windows.Foundation.DeprecatedAttribute к коду в управляемых сборках; Это может стать причиной предупреждения при построении.|  
|Область|Пограничный случай|  
|Версия|4.5.1|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0048A<br /><br /> CD0048B|  
  
<a name="diagnostic49"></a>   
## <a name="49-resolveassemblyreference-task-now-warns-on-dependencies-with-the-wrong-architecture"></a>49: зависимости с помощью неправильного архитектуры теперь предупреждает ResolveAssemblyReference-задача  
  
|||  
|-|-|  
|Подробные сведения|Задача выдает предупреждение (MSB3270), которое означает, что ссылка или ее зависимости не соответствуют архитектуре приложения. Например, это происходит, если приложение, скомпилированное с параметром anycpu включает x86 ссылки. Такой сценарий может привести к сбою приложения во время выполнения (в этом случае: если приложение развертывается как&64;-разрядный процесс).|  
|Предложение|Существует две области влияния.<br /><br /> Во время перекомпиляции выдаются предупреждения, которые отсутствовали при компиляции в предыдущей версии MSBuild. Однако поскольку в предупреждении указан возможный источник ошибки среды выполнения, его следует проверить.<br /><br /> Если предупреждения считаются ошибками, приложение скомпилировано не будет.|  
|Область|Дополнительный номер|  
|Версия|4.5.1|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0049|  
  
<a name="diagnostic51"></a>   
## <a name="51-wpf-textbox-defaults-to-undo-limit-of-100"></a>51: WPF TextBox по умолчанию для отмены ограничение в 100  
  
|||  
|-|-|  
|Подробные сведения|В .NET 4.5 ограничение отмены по умолчанию для текстового поля WPF — 100 (в отличие от неограниченное в .NET 4.0)|  
|Предложение|В случае слишком низкой отмены ограничение в 100 ограничение можно задать явным образом свойство UndoLimit текстовое поле|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Windows.Controls.TextBox?displayProperty=fullName>|  
|Анализаторы|CD0051|  
  
<a name="diagnostic55"></a>   
## <a name="55-exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>55: исключения во время обработки без наблюдения в System.Threading.Tasks.Task больше не распространяется на поток метода завершения  
  
|||  
|-|-|  
|Подробные сведения|Поскольку класс System.Threading.Tasks.Task представляет асинхронную операцию, он перехватывает все исключения невысокой, возникающие во время асинхронной обработки. В .NET Framework 4.5, если исключение не наблюдается и код никогда не ожидает задачу, исключение больше не распространяется на поток метода завершения и приводит к сбою процесса во время сборки мусора. Это изменение повышает надежность приложений, используйте класс задачи для выполнения асинхронной обработки без наблюдения.|  
|Предложение|Если приложение зависит от непредвиденное асинхронных исключений, распространение на поток финализации, можно восстановить прежнее поведение, предоставив соответствующий обработчик для [TaskScheduler.UnobservedTaskException](https://msdn.microsoft.com/en-us/library/system.threading.tasks.taskscheduler.unobservedtaskexception\(v=vs.110\).aspx) событий, или установив [элемента конфигурации среды выполнения](https://msdn.microsoft.com/en-us/library/jj160346%28v=vs.110%29.aspx).|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Threading.Tasks.Task.Run%28System.Action%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Action%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%60%600%7D%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Run%60%601%28System.Func%7B%60%600%7D%2CSystem.Threading.CancellationToken%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.Task.Start%28System.Threading.Tasks.TaskScheduler%29?displayProperty=fullName>|  
|Анализаторы|CD0055|  
  
<a name="diagnostic58"></a>   
## <a name="58-iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a>58: свойство IAsyncResult.CompletedSynchronously должна быть правильной результирующая задача завершилась  
  
|||  
|-|-|  
|Подробные сведения|При вызове TaskFactory.FromAsync, реализация свойства IAsyncResult.CompletedSynchronously должна быть правильной результирующая задача завершилась. То есть свойство должно возвращать значение true, если и только если реализация завершилась синхронно. Раньше свойство не проверялось.|  
|Предложение|При реализации IAsyncResult правильно возвращает значение true для свойства CompletedSynchronusly только тогда, когда задача завершилась синхронно, будет наблюдаться без разрыва. Пользователи должны проверить реализации IAsyncResult, которыми они владеют (если таковые имеются), чтобы убедиться, что они правильно оценить ли задача завершена синхронно или нет.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%29?displayProperty=fullName> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%28System.IAsyncResult%2CSystem.Action%7BSystem.IAsyncResult%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7BSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName> </TArg1, AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, AsyncCallback, Object, IAsyncResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%60%600%7D%2CSystem.Threading.Tasks.TaskCreationOptions%2CSystem.Threading.Tasks.TaskScheduler%29?displayProperty=fullName> \</IAsyncResult, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, AsyncCallback, Object, IAsyncResult> \</TArg1, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%601%7D%2C%60%600%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, AsyncCallback, Object, IAsyncResult> \</TArg1, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName> </TArg1, TArg2, AsyncCallback, Object, IAsyncResult> </TArg1, TArg2><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%602%7D%2C%60%600%2C%60%601%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName> </TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> </TArg1, TArg2, TArg3><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Action%7BSystem.IAsyncResult%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3, TResult><br /><br /> <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604%28System.Func%7B%60%600%2C%60%601%2C%60%602%2CSystem.AsyncCallback%2CSystem.Object%2CSystem.IAsyncResult%7D%2CSystem.Func%7BSystem.IAsyncResult%2C%60%603%7D%2C%60%600%2C%60%601%2C%60%602%2CSystem.Object%2CSystem.Threading.Tasks.TaskCreationOptions%29?displayProperty=fullName> \</IAsyncResult, TResult> \</TArg1, TArg2, TArg3, AsyncCallback, Object, IAsyncResult> \</TArg1, TArg2, TArg3, TResult>|  
|Анализаторы|CD0058|  
  
<a name="diagnostic59"></a>   
## <a name="59-log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>59: имя файла журнала, созданные методом ObjectContext.CreateDatabase изменилось на соответствует спецификациям SQL Server  
  
|||  
|-|-|  
|Подробные сведения|Если метод CreateDatabase вызывается либо непосредственно или с помощью Code First с поставщиком SqlClient и значение AttachDBFilename в строке подключения, он создает файл журнала с именем filename_log.ldf вместо filename.ldf (где имя файла — имя файла, указанного в значении AttachDBFilename). Это изменение улучшает отладку, предоставляя файл журнала, имя которого соответствует спецификациям SQL Server.|  
|Предложение|Если имя файла журнала является важной для приложения, приложения должны обновляться ожидать _log.ldf стандартный формат имени файла.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>|  
|Анализаторы|CD0059|  
  
<a name="diagnostic60"></a>   
## <a name="60-pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>60: Page.LoadComplete событие больше не заставляет элемент управления System.Web.UI.WebControls.EntityDataSource вызывать привязку данных  
  
|||  
|-|-|  
|Подробные сведения|`Page.LoadComplete` Событие больше не заставляет элемент управления System.Web.UI.WebControls.EntityDataSource вызывать привязку данных для изменения параметров создания, обновления и удаления. Это изменение исключает лишнее обращение к базе данных, предотвращает сброса значений элементов управления и позволяет получить поведение, согласованное с другими элементами управления данными, такие как SqlDataSource и ObjectDataSource. Это изменение дает другое поведение в том маловероятном случае, когда в приложении предполагается вызов привязки данных в событии `Page.LoadComplete`.|  
|Предложение|При необходимости для привязки данных, вручную вызова databind в событии, которое ранее в обратной передаче.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0060|  
  
<a name="diagnostic61"></a>   
## <a name="61-webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>61: WebUtility.HtmlDecode больше не декодирует Недопустимый входной последовательности.  
  
|||  
|-|-|  
|Подробные сведения|По умолчанию методы декодирования больше не декодируют недопустимую входную последовательность в недопустимую строку UTF-16. Вместо этого они возвращают исходные входные данные.|  
|Предложение|Изменение в выходных данных декодера может иметь значение, только если в строках хранятся двоичные данные, а не данные UTF-16. Чтобы явно контролировать это поведение, присвойте `aspnet:AllowRelaxedUnicodeDecoding` атрибут [appSettings](https://msdn.microsoft.com/en-us/library/ms228154\(v=vs.110\).aspx) равным true, чтобы разрешить устаревшее поведение, или значение false, чтобы разрешить текущее поведение.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Net.WebUtility.HtmlDecode%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.HtmlDecode%28System.String%2CSystem.IO.TextWriter%29?displayProperty=fullName><br /><br /> <xref:System.Net.WebUtility.UrlDecode%28System.String%29?displayProperty=fullName>|  
|Анализаторы|CD0061|  
  
<a name="diagnostic63"></a>   
## <a name="63-apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>63: приложения с помощью ClickOnce, использующие сертификат подписи кода SHA-256, может произойти сбой в системе Windows 2003  
  
|||  
|-|-|  
|Подробные сведения|Исполняемый файл подписывается с помощью SHA256. Ранее он подписывался с помощью SHA1 независимо от того, какой использовался сертификат подписи кода: SHA-1 или SHA-256. Применение:<br /><br /> Все приложения, собранные с помощью Visual Studio 2012 или более поздней версии.<br /><br /> Приложения, собранные с помощью Visual Studio 2010 или более ранней версии в системах с установленной платформой .NET Framework 4.5.<br /><br /> Кроме того, при наличии .NET Framework 4.5 или более поздней версии манифест ClickOnce также подписывается с помощью SHA-256 для сертификатов SHA-256 независимо от версии .NET Framework, в которой проводилась компиляция.|  
|Предложение|Изменение подписи исполняемого файла ClickOnce влияет только на системы Windows Server 2003; они требуют наличия Статьи базы знаний 938397.<br /><br /> Изменение подписи манифеста с SHA-256, даже если целевая платформа приложения — .NET Framework 4.0 или более ранней версии, вводит зависимость среды выполнения для .NET Framework 4.5 или более поздней версии.|  
|Область|Пограничный случай|  
|Версия|4.5-4.6|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0063|  
  
<a name="diagnostic68"></a>   
## <a name="68-dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>68: DbParameter.Precision и DbParameter.Scale теперь являются открытые виртуальные члены  
  
|||  
|-|-|  
|Подробные сведения|DbParameter.Precision и DbParameter.Scale реализованы как открытые виртуальные свойства. Они заменяют соответствующие явные реализации интерфейса, DbParameter.IDbDataParameter.Precision и DbParameter.IDbDataParameter.Scale.|  
|Предложение|Создавая заново поставщика базы данных ADO.NET, эти различия потребует ключевое слово «override» для применения к свойства точности и масштаба. Это требуется только в случае повторного создания компонентов; существующий двоичные файлы будут продолжать работать.|  
|Область|Дополнительный номер|  
|Версия|4.5.1|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.Data.Common.DbParameter.Precision?displayProperty=fullName><br /><br /> <xref:System.Data.Common.DbParameter.Scale?displayProperty=fullName>|  
|Анализаторы|CD0068|  
  
<a name="diagnostic73"></a>   
## <a name="73-dataobjectgetdata-now-retrieves-data-as-utf-8"></a>73: DataObject.GetData теперь получает данные в кодировке UTF-8  
  
|||  
|-|-|  
|Подробные сведения|Для приложений, предназначенных для .NET Framework 4 или под управлением .NET Framework 4.5.1 или более ранних версий DataObject.GetData извлекает данные в формате HTML как строки ASCII. В результате символы, не относящиеся к ASCII (т. е. символы с кодами ASCII больше 0x7F), представляются двумя случайными символами.<br /><br /> Для приложений, предназначенных для .NET Framework 4.5 или более поздней версии и выполняемых в .NET Framework 4.5.2 `DataObject.GetData` извлекает данные в формате HTML в кодировке UTF-8, правильно представляет символы с кодами более 0x7F.|  
|Предложение|Если реализован обходной путь для проблемы с HTML-строк кодировкой (например, явная кодировка HTML-строки, полученной из буфера обмена путем ее передачи в метод UTF8Encoding.GetString) и выполняется изменение целевой платформы приложения с версии 4-4.5, следует удалить этот обходной путь.<br /><br /> Если для какой-либо причине требуется старое поведение, приложения можно ориентироваться на .NET Framework 4.0, чтобы добиться этого поведения.|  
|Область|Пограничный случай|  
|Версия|4.5.2|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.Windows.DataObject.GetData%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.String%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Windows.DataObject.GetData%28System.Type%29?displayProperty=fullName>|  
|Анализаторы|CD0073|  
  
<a name="diagnostic75"></a>   
## <a name="75-targetframeworkname-for-default-app-domain-no-longer-defaults-to-null-if-not-set"></a>75: TargetFrameworkName для домена приложения по умолчанию больше не по умолчанию имеет значение null, если оно не задано  
  
|||  
|-|-|  
|Подробные сведения|TargetFrameworkName был ранее null в домене приложения по умолчанию, если не было задано явно. Начиная с 4.6, свойство TargetFrameworkName для домена приложения по умолчанию будет иметь значение по умолчанию, производный от TargetFrameworkAttribute (если она доступна). Домены приложений не по умолчанию будет наследовать их TargetFrameworkName домена приложения по умолчанию (который не будет по умолчанию NULL в 4.6), если она явно не переопределено.|  
|Предложение|Следует обновить код, не зависят от `AppDomainSetup.TargetFrameworkName` по умолчанию null. Если это требуется, это свойство будет продолжать присвоено значение null, он может быть явно присвоено значение.|  
|Область|Пограничный случай|  
|Версия|4.6|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.AppDomainSetup.TargetFrameworkName?displayProperty=fullName>|  
|Анализаторы|CD0075B<br /><br /> CD0075A|  
  
<a name="diagnostic76"></a>   
## <a name="76-x509certificate2tostringbool-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>76: X509Certificate2.ToString(bool) не создает исключение, теперь когда .NET не удается обработать сертификата  
  
|||  
|-|-|  
|Подробные сведения|Ранее, этот метод может генерировать Если «true» для был передан параметр verbose и были установлены сертификаты, не поддерживаемые .net Framework. Теперь метод успешным и возвращать допустимое строковое выражение, опускает недоступной части certifiate.|  
|Предложение|Любой код, в зависимости от X509Certificate2.ToString(bool) должны обновляться следует ожидать, возвращаемая строка может исключить некоторые данные сертификата (например, открытый ключ, закрытый ключ и расширения), в некоторых случаях, в которых API будет ранее исключение.|  
|Область|Пограничный случай|  
|Версия|4.6|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|  
|Анализаторы|CD0076|  
  
<a name="diagnostic77"></a>   
## <a name="77-reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>77: отражение объектов могут больше не передаваться из управляемого кода DCOM-клиентам out of process  
  
|||  
|-|-|  
|Подробные сведения|Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM. Затрагиваются следующие типы:<br /><br /> Assembly<br /><br /> MemberInfo (и его производные типы, включая FieldInfo, MethodInfo, тип и TypeInfo)<br /><br /> MethodBody<br /><br /> Модуль<br /><br /> Объект ParameterInfo.<br /><br /> Вызовы `IMarshal` для возврата объекта `E_NOINTERFACE`.|  
|Предложение|Обновите код для работы с объектами без отражения|  
|Область|Дополнительный номер|  
|Версия|4.6|  
|Тип|Среда выполнения|  
|Анализаторы|CD0077|  
  
<a name="diagnostic78"></a>   
## <a name="78-contentdisposition-datetimes-returns-slightly-different-string"></a>78: ContentDisposition даты возвращает немного другую строку  
  
|||  
|-|-|  
|Подробные сведения|Строковые представления ContentDispositions были обновлены, начиная с 4.6, чтобы всегда представляют компонент часа даты и времени с двумя цифрами. Это в соответствии с [RFC822](http://www.ietf.org/rfc/rfc0822.txt) и [RFC2822](http://www.ietf.org/rfc/rfc2822.txt). В результате `ContentDisposition.ToString` для возврата немного другую строку в 4.6 в сценариях, где один из элементов времени обработки был до 10:00. Обратите внимание, что ContentDispositions сериализуются иногда посредством преобразования их в строки, поэтому следует просмотреть все операции ContentDisposition ToString, сериализации или GetHashCode вызовы.|  
|Предложение|Не ожидается, что строковые представления ContentDispositions из разных версий .NET Framework будут правильно сравнивать друг с другом. Преобразование строк ContentDispositions, если это возможно, перед проведением сравнения.|  
|Область|Дополнительный номер|  
|Версия|4.6|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=fullName><br /><br /> <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=fullName>|  
|Анализаторы|CD0078|  
  
<a name="diagnostic82"></a>   
## <a name="82-workflowdesignerload-doesnt-remove-symbol-property"></a>82: WorkflowDesigner.Load не удаляет символ свойства  
  
|||  
|-|-|  
|Подробные сведения|Если для различных версий платформы .NET Framework 4.5 в конструкторе рабочих процессов и загрузки рабочих процессов повторного размещения 3.5 с помощью метода WorkflowDesigner.Load(), XamlDuplicateMemberException, вызывается исключение при сохранении рабочего процесса.|  
|Предложение|Эта ошибка только манифесты при нацеливании на .NET Framework 4.5 в конструкторе рабочих процессов, поэтому ее можно обойти, установив `WorkflowDesigner.Context.Services.GetService<DesignerConfigurationService>().TargetFrameworkName` в 4.0 .NET Framework.<br /><br /> Кроме того, эту проблему можно избежать с помощью [WorkflowContext.Load(string)](https://msdn.microsoft.com/en-us/library/ee425926\(v=vs.110\).aspx) метод для загрузки рабочего процесса, а не [WorkflowDesigner.Load()](https://msdn.microsoft.com/en-us/library/ee403482\(v=vs.110\).aspx).|  
|Область|Значительно|  
|Версия|4.5-4.5.2|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=fullName>|  
|Анализаторы|CD0082|  
  
<a name="diagnostic83"></a>   
## <a name="83-sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>83: SqlConnection.Open завершается на Windows 7 не IFS Winsock BSP или LSP присутствует  
  
|||  
|-|-|  
|Подробные сведения|SqlConneciton.Open и OpenAsync в .NET Framework 4.5 ошибкой, если не запущена на компьютере Windows 7 с не IFS Winsock BSP или LSP присутствует на компьютере.<br /><br /> Чтобы определить, установлен ли загрузочного IFS Процессора или LSP, используйте `netsh WinSock Show Catalog` команды и просмотрите каждый `Winsock Catalog Provider Entry` элемент, который возвращается. Если имеет значение флагов службы `0x20000` битом, поставщик использует маркеры IFS и будет работать правильно. Если `0x20000` бит снят (не задано), это загрузочный IFS Процессор или LSP.|  
|Предложение|Это ошибка исправлена в .NET Framework 4.5.2, поэтому его можно избежать путем обновления .NET Framework. Кроме того его можно избежать, удалив все установленные не - IFS LSP Winsock.|  
|Область|Дополнительный номер|  
|Версия|4.5-4.5.2|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=fullName><br /><br /> <xref:System.Data.SqlClient.SqlConnection.OpenAsync%28System.Threading.CancellationToken%29?displayProperty=fullName>|  
|Анализаторы|CD0083|  
  
<a name="diagnostic84"></a>   
## <a name="84-icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>84: изменить поведение ICommand.CanExecuteChanged событий в .NET 4.5  
  
|||  
|-|-|  
|Подробные сведения|В платформе .NET Framework 4.5 CanExecuteChangedEvent был пропускаются, если отправитель события был один и тот же объект как объект, вызвавший событие. Эта ошибка была исправлена в servcing обновления .NET Framework 4.5.|  
|Предложение|Эта ошибка была исправлена в .NET Framework 4.5 обслуживания выпусков, поэтому его можно избежать, убедившись, что платформа .NET Framework не требует обновления или обновления для .NET Framework 4.5.1. Кроме того чтобы убедиться в том, что отправитель при вызове команды CanExecuteChanged является таким же, как объект, вызывающий события можно изменить код приложения с использованием ICommand.|  
|Область|Дополнительный номер|  
|Версия|4.5-4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=fullName>|  
|Анализаторы|CD0084|  
  
<a name="diagnostic85"></a>   
## <a name="85-some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>85: некоторые интерфейсы API .NET вызвать первого экземпляра (обработано) EntryPointNotFoundExceptions  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.5 небольшое количество методов .NET начала создания первого экземпляра EntryPointNotFoundExceptions. Эти исключения обрабатывались в .net Framework, но может привести к нарушению автоматизации тестирования, которые не ожидал исключений первого шанса. Тех же интерфейсов API препятствует работе некоторых сценариев ApiVerifier при включении HighVersionLie.|  
|Предложение|Этой ошибки можно избежать путем обновления для .NET Framework 4.5.1. Кроме того можно обновить автоматизации тестирования не прерывать выполнение при первичном EntryPointNotFoundExceptions.|  
|Область|Пограничный случай|  
|Версия|4.5-4.5.1|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Diagnostics.Debug.Assert%28System.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%29?displayProperty=fullName><br /><br /> <xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%29?displayProperty=fullName><br /><br /> [Метод Debug.Assert (логическое значение, строка, строка, объект\<xref:System.Diagnostics.Debug.Assert%28System.Boolean%2CSystem.String%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName><br /><br /> <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%29?displayProperty=fullName>|  
|Анализаторы|CD0085|  
  
<a name="diagnostic86"></a>   
## <a name="86-scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>86: прокрутка TreeView в WPF или сгруппированные ListBox в VirtualizingStackPanel может привести к зависанию  
  
|||  
|-|-|  
|Подробные сведения|В версии .NET Framework&4;.5 прокрутка TreeView WPF на панели виртуализированных стека может привести к зависает при наличии полей в области просмотра (между элементами в дереве, например, или элемент ItemsPresenter). Кроме того в некоторых случаях различных размеров элементов в представлении может привести к нестабильности даже при наличии без полей.|  
|Предложение|Этой ошибки можно избежать путем обновления для .NET Framework 4.5.1. Кроме того поля можно удалить из представления коллекций (например, элементов TreeView) панелях виртуализированных стека, если все содержащиеся в них элементы имеют одинаковый размер.|  
|Область|Значительно|  
|Версия|4.5-4.5.1|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing%28System.Windows.DependencyObject%2CSystem.Boolean%29?displayProperty=fullName>|  
|Анализаторы|CD0086<br /><br /> CD0086|  
  
<a name="diagnostic89"></a>   
## <a name="89-typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>89: Type.IsAssignableFrom возвращает неверный результат для универсальных переменных с ограничениями  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.5 неправильно возвратит Type.IsAssignableFrom `false` во всех случаях некоторые универсальных типов с ограничениями.|  
|Предложение|Эта проблема была исправлена в обновлении обслуживания. Обновите .NET Framework 4.5, или обновления для .NET Framework 4.5.1 или более поздней версии, чтобы устранить эту проблему. Кроме того Избегайте использования IsAssignableFrom с универсальными типами, которые имеют ограничения для универсальных параметров. Интерфейсы API для отражения может служить обхода.|  
|Область|Дополнительный номер|  
|Версия|4.5-4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Type.IsAssignableFrom%28System.Type%29?displayProperty=fullName>|  
|Анализаторы|CD0089<br /><br /> CD0089|  
  
<a name="diagnostic91"></a>   
## <a name="91-entityframework-60-loads-very-slowly-in-apps-launched-from-visual-studio"></a>91: EntityFramework 6.0 очень медленно загружает в приложениях, запускаемых из Visual Studio  
  
|||  
|-|-|  
|Подробные сведения|Запуск приложения из Visual Studio 2013, которая использует EntityFramework 6.0 может работать очень медленно.|  
|Предложение|Эта проблема решена в EntityFramework 6.0.2. Обновите EntityFramework, чтобы избежать проблем с производительностью.|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0091|  
  
<a name="diagnostic92"></a>   
## <a name="92-multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>92: изменить интервалы ASP.Net многострочного текстового поля при использовании AntiXSSEncoder  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.0, лишние строки были вставлены между строками многострочное текстовое поле, при обратной передаче, если с помощью `AntiXSSEncoder`. В .NET Framework 4.5 эти дополнительные переносы не включены, но только в том случае, если веб-приложение предназначено для .NET 4.5|  
|Предложение|Имейте в виду, что перенаправлены на .NET 4.5 4.0 веб-приложения могут иметь многострочных текстовых полей, улучшена, чтобы вставить дополнительные переносы строк больше не. Если это нежелательно, приложение может получить старое поведение при запуске в .NET Framework 4.5, предназначенные для .NET Framework 4.0.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0092|  
  
<a name="diagnostic95"></a>   
## <a name="95-concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>95: ConcurrentQueue<>\>. TryPeek может возвращать ошибочные null через его выходной параметр  
  
|||  
|-|-|  
|Подробные сведения|В некоторых сценариях с несколькими потоками `ConcurentQueue<T>.TryPeek` возвращает значение true, но заполнения выходной параметр со значением null (а не значение правильно, считанный).|  
|Предложение|Эта проблема решена в .NET Framework 4.5.1. Обновление до этой платформы будет решить проблему.|  
|Область|Значительно|  
|Версия|4.5-4.5.1|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek%28%600%40%29?displayProperty=fullName>|  
|Анализаторы|CD0095|  
  
<a name="diagnostic98"></a>   
## <a name="98-multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>98: можно упорядочить несколько элементов в одной ячейке TableLayoutPanel  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.5 Если несколько элементов, помещаются в одну и ту же ячейку TableLayoutPanel, они может отображаться в другом порядке, чем они находились в .NET Framework 4.0.|  
|Предложение|Это была возвращена в обслуживания обновления для .NET Framework 4.5. Обновите .NET Framework 4.5, или обновления для .NET Framework 4.5.1 или более поздней версии, чтобы устранить эту проблему. Кроме того Избегайте неоднозначных случай несколько элементов в одной и той же ячейке TableLayourPanel.|  
|Область|Дополнительный номер|  
|Версия|4.5-4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Windows.Forms.TableLayoutControlCollection.Add%28System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>|  
|Анализаторы|CD0098|  
  
<a name="diagnostic100"></a>   
## <a name="100-foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>100: переменной итератора Foreach теперь относятся в рамках итерации, поэтому замыкания записи семантика отличается (в C#&5;)  
  
|||  
|-|-|  
|Подробные сведения|Начиная с C# 5 (Visual Studio 2012), foreach переменных-итераторов действуют в рамках итерации. Это может вызвать разрывы, если код был ранее в зависимости от переменных, не будут включены в замыкание foreach. Признаком это изменение будет что переменная-итератор передаваемый delagate будет рассматриваться как значение, которое он имел во время создания делегата, а не значение, которое он имел во время вызова делегата.|  
|Предложение|В идеале следует обновить код, следует ожидать новое поведение компилятора. Если требуются старые семантики, можно заменить переменной итератора отдельной переменной, которое явным образом помещается за пределами видимости этого цикла.|  
|Область|Значительно|  
|Версия|4.5|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0100|  
  
<a name="diagnostic101"></a>   
## <a name="101-htmltextwriter-does-not-render-br-element-correctly"></a>101: HtmlTextWriter не отображается.\`<br>\>"элемент правильно  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.6, вызвав `HtmlTextWriter.RenderBeginTag()` и `HtmlTextWriter.RenderEndTag()` с `<BR />` элемент правильно вставить только один `<BR />` (вместо двух)|  
|Предложение|Если приложение зависит от дополнительного `<BR />` тег, `HtmlTextWriter.RenderBeginTag()` должен быть вызван второй раз. Обратите внимание, что это изменение влияет только на приложения, ориентированные на .NET Framework 4.6, поэтому другим вариантом является предназначенные для предыдущей версии платформы .NET Framework для получения старого поведения.|  
|Область|Пограничный случай|  
|Версия|4.6|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.String%29?displayProperty=fullName><br /><br /> <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>|  
|Анализаторы|CD0101|  
  
<a name="diagnostic104"></a>   
## <a name="104-calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>104: вызов Items.Refresh в WPF-элемент ListBox, ListView или DataGrid с выбранным элементов может привести к повторяющиеся элементы для отображения в элементе  
  
|||  
|-|-|  
|Подробные сведения|В .NET Framework 4.5 вызов ListBox.Items.Refresh из кода, при выборе элементов в ListBox может привести к дублироваться в списке Выбранные элементы. Такая же проблема возникает с ListView и DataGrid. Эта проблема устранена в .NET Framework 4.6.|  
|Предложение|Эта проблема может обойти, программным путем снятия выделения элементов до вызова обновления и повторно выбрав их после завершения вызова. Кроме того эта проблема была устранена в .NET Framework 4.6 и может быть устранена путем обновления до новой версии платформы .NET Framework.|  
|Область|Дополнительный номер|  
|Версия|4.5-4.6|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName>|  
|Анализаторы|CD0104|  
  
<a name="diagnostic105"></a>   
## <a name="105-etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>105: EventListeners трассировки событий Windows не выполняется сбор событий от поставщиков с явной ключевые слова (например, поставщик библиотека параллельных задач)  
  
|||  
|-|-|  
|Подробные сведения|EventListeners трассировки событий Windows с помощью маски пустой ключевое слово правильно не записываются события от поставщиков с помощью явного ключевых слов. В платформе .NET Framework 4.5 поставщика TPL началось, предоставляя явные ключевые слова и вызвана эта проблема. В .NET Framework 4.6 EventListeners были обновлены на нет эту проблему.|  
|Предложение|Чтобы обойти эту проблему, замените вызовы EnableEvents перегрузку, которая явно задает маску «любые ключевые слова» использовать вызовы EnableEvents (eventSource, уровня): `EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))`.<br /><br /> Кроме того эта проблема была устранена в .NET Framework 4.6 и может быть устранена путем обновления до новой версии платформы .NET Framework.|  
|Область|Пограничный случай|  
|Версия|4.5-4.6|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Diagnostics.Tracing.EventListener.EnableEvents%28System.Diagnostics.Tracing.EventSource%2CSystem.Diagnostics.Tracing.EventLevel%29?displayProperty=fullName>|  
|Анализаторы|CD0105|  
  
<a name="diagnostic109"></a>   
## <a name="109-building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>109: построение edmx Entity Framework с помощью Visual Studio 2013 возможен сбой с ошибкой MSB4062, если с помощью EntityDeploySplit или EntityClean задач  
  
|||  
|-|-|  
|Подробные сведения|MSBuild 12.0 инструментах (в Visual Studio 2013) изменить расположение файлов msbuild, приводит к старой Entity Framework целевых файлов недействительности. В результате `EntityDeploySplit` и `EntityClean` задачи завершаться сбоем, поскольку не удается найти `Microsoft.Data.Entity.Build.Tasks.dll`. Обратите внимание, что этот разрыв вследствие изменения набора инструментов (msbuild и Visual STUDIO), из-за изменения платформы .NET Framework. Только произойдет при обновлении средств разработчика, не обновляя просто .NET Framework.|  
|Предложение|Для работы с началом нового макета msbuild в .NET Framework 4.6 фиксированы Entity Framework целевых файлов. Обновление до новой версии платформы, эта неполадка будет устранена. Кроме того [это](http://stackoverflow.com/a/24249247/131944) решение можно использовать для исправления целевых файлов напрямую.|  
|Область|Значительно|  
|Версия|4.5.1-4.6|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0109|  
  
<a name="diagnostic111"></a>   
## <a name="111-xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>111: проверки XSD-схемы теперь правильно обнаруживает нарушений ограничений unique, если используются составные ключи и один раздел пуст  
  
|||  
|-|-|  
|Подробные сведения|Версии платформы .NET Framework, предшествовавших 4.6 были ошибки, вызвавшей проверку XSD не обнаруживать ограничения unique на составные ключи, если один из ключей пуст. Эта проблема решена в .NET Framework 4.6. Это приведет к более правильной проверки, но он может привести к проверке которой ранее бы XML-код.|  
|Предложение|Если менее тесной, требуется проверка .NET Framework 4.0, проверяющий приложение предназначено для версии 4.5 (или более ранней) платформы .NET Framework. При целевой платформы для .NET 4.6, тем не менее, чтобы убедиться, что повторяющиеся составные ключи (как описано в описании этой проблемы) не предполагается, что проверка следует выполнять проверку кода.|  
|Область|Пограничный случай|  
|Версия|4.6|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0111|  
  
<a name="diagnostic112"></a>   
## <a name="112-calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a>112: вызов Attribute.GetCustomAttributes на свойство индексатора больше не вызывает AmbiguousMatchException, если типом индекса для устранения неоднозначности  
  
|||  
|-|-|  
|Подробные сведения|До .NET Framework 4.6, вызвав `GetCustomAttribute(s)` для индексатора, которое отличается от другого свойства только для типа индекса приведет к `AmbiguousMatchException`. Начиная с .NET Framework 4.6, атрибуты свойства правильно возвращается.|  
|Предложение|Имейте в виду, теперь чаще работать GetCustomAttribute(s). Если приложение ранее полагаться на `AmbiguousMatchException`, теперь должны использовать отражение для явного поиска для нескольких индексаторов вместо.|  
|Область|Пограничный случай|  
|Версия|4.6|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Attribute.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%28System.Reflection.MemberInfo%2CSystem.Type%2CSystem.Boolean%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%29?displayProperty=fullName><br /><br /> <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601%28System.Reflection.MemberInfo%2CSystem.Boolean%29?displayProperty=fullName>|  
|Анализаторы|CD0112|  
  
<a name="diagnostic113"></a>   
## <a name="113-intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>113: периодически удалось прокрутите до нижней элемента в ItemsControls (например, ListBox и DataGrid) при использовании пользовательских DataTemplates  
  
|||  
|-|-|  
|Подробные сведения|В некоторых случаях ошибки в .NET Framework 4.5 вызывающую ItemsControls (например, ListBox, ComboBox, DataGrid, и т.д.) не прокрутки на их нижний элемент при использовании пользовательских DataTemplates. Если прокрутки предпринимается попытка повторно (после прокрутку вверх), работа будет затем.|  
|Предложение|Эта проблема была устранена в .NET Framework 4.5.2 и может быть устранена путем обновления до этой версии (или более поздней версии) платформы .NET Framework. Кроме того пользователи по-прежнему можно перетаскивать полосы прокрутки в окончательный элементы в этих коллекциях, но может потребоваться дважды, в этом случае успешно.|  
|Область|Дополнительный номер|  
|Версия|4.5-4.5.2|  
|Тип|Среда выполнения|  
|Анализаторы|CD0113|  
  
<a name="diagnostic114"></a>   
## <a name="114-glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-45"></a>114: GlyphRun.ComputeInkBoundingBox() и FormattedText.Extent возвращают различные значения, начиная с .NET 4.5  
  
|||  
|-|-|  
|Подробные сведения|Были сделаны усовершенствования GlyphRun.ComputeInkBoundingBox() и FormattedText.Extent в .NET Framework 4.5 для решения проблем, где поля были слишком мало для автономной глифы в некоторых случаях в .NET Framework 4.0. В результате этого некоторые ограничивающие прямоугольники будет больше, начиная с .NET Framework 4.5, что приводит к небольшие отличия в макет пользовательского интерфейса.|  
|Предложение|Имейте в виду, что увеличиться некоторые размеры глиф ограничивающего поля. Эти изменения обычно улучшит презентации и проверка попадания поле, но при необходимости старых поведение (до .NET 4.5), его можно включить, добавив следующую запись в файл app.config.<br /><br /> `<appsettings> <add key="IncludeAllInkInBoundingBox" value="false"> </appsettings>`|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=fullName><br /><br /> <xref:System.Windows.Media.FormattedText.Extent?displayProperty=fullName>|  
|Анализаторы|CD0114|  
  
<a name="diagnostic124"></a>   
## <a name="124-calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>124: вызов метода DataGrid.CommitEdit из обработчика CellEditEnding удаляет фокус  
  
|||  
|-|-|  
|Подробные сведения|Вызов DataGrid.CommitEdit один из обработчиков событий элемента управления DataGrid CellEditEnding заставляет DataGrid теряет фокус.|  
|Предложение|Это ошибка исправлена в .NET Framework 4.5.2, поэтому его можно избежать путем обновления .NET Framework. Кроме того его можно избежать, явно повторно выбрав DataGrid после вызова CommitEdit.|  
|Область|Пограничный случай|  
|Версия|4.5-4.5.2|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName><br /><br /> <xref:System.Windows.Controls.DataGrid.CommitEdit%28System.Windows.Controls.DataGridEditingUnit%2CSystem.Boolean%29?displayProperty=fullName>|  
|Анализаторы|CD0124|  
  
<a name="diagnostic125"></a>   
## <a name="125-aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>125: ASP.NET MVC теперь экранирует пробелы в строках, переданный через параметры маршрута  
  
|||  
|-|-|  
|Подробные сведения|Чтобы соответствовать стандарту RFC 2396 пробелами в путях маршрута, теперь исключаются при заполнении параметров действий из маршрута. Таким образом в то время как `/controller/action/some data` ранее будет соответствовать маршрута `/controller/action/{data}` и предоставить `some data` как параметр данных теперь предоставит `some%20data` вместо.|  
|Предложение|Код должен быть обновлен для unescape строковых параметров из маршрута. При необходимости исходный URI может осуществляться с помощью интерфейса API Request.RequestUri.OriginalString.|  
|Область|Дополнительный номер|  
|Версия|4.5.2|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Web.Http.RouteAttribute.%23ctor%28System.String%29?displayProperty=fullName>|  
|Анализаторы|CD0125|  
  
<a name="diagnostic127"></a>   
## <a name="127-vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>127: VB.NET больше не поддерживает квалификации частичные пространства имен System.Windows API-интерфейсы  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET 4.5.2, проектах VB.NET невозможно задать System.Windows API-интерфейсы с частично указанием пространства имен. Например, ссылающегося на `Windows.Forms.DialogResult` завершится ошибкой. Вместо этого код должен ссылаться на полное доменное имя (`System.Windows.Forms.DialogResult`) или импортировать указанным пространством имен и ссылаться просто в `DialogResult`.|  
|Предложение|Следует обновить код для ссылки на `System.Windows` интерфейсы API, с помощью полных имен или с простых имен (и импорта соответствующего пространства имен).|  
|Область|Дополнительный номер|  
|Версия|4.5.2|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0127|  
  
<a name="diagnostic129"></a>   
## <a name="129-two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>129: двухсторонней привязки данных к свойству с помощью setter неоткрытые не поддерживается.  
  
|||  
|-|-|  
|Подробные сведения|Попытка привязки данных к свойству без открытого переключателя не было поддерживается. Начиная с .NET Framework 4.5.1, этот сценарий выдаст исключение InvalidOperationException. Обратите внимание, что это новое исключение возникает только для приложений, которые предназначены специально для .NET Framework 4.5.1. Если приложение предназначено для платформы .NET Framework 4.5, вызов будет разрешен. Если приложение не предназначены для определенной версии .NET Framework, привязка будет рассматриваться как односторонние.|  
|Предложение|Приложения должен быть обновлен для односторонней привязки, либо использовать публично предоставляют метод задания свойства. Кроме того выбор .NET Framework 4.5 вызовет старой поведение приложения.|  
|Область|Дополнительный номер|  
|Версия|4.5.1|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.Windows.Data.BindingMode?displayProperty=fullName>|  
|Анализаторы|CD0129|  
  
<a name="diagnostic130"></a>   
## <a name="130-marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>130: Marshal.SizeOf и Marshal.PtrToStructure перегрузки break динамического кода  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.5.1, динамическая привязка к методам `Marshal.SizeOf` или `Marshal.PtrToStructure` (с помощью Windows PowerShell, IronPython или C# ключевое слово dynamic, например) может привести к `MethodInvocationExceptions` так, как были добавлены новые перегрузки этих методов, которые могут быть неоднозначным для обработчиков сценариев.|  
|Предложение|Обновление скриптов для обозначения какие shouldbe перегрузка используется. Это обычно решается путем явного приведения типа параметров как можно `System.Type`. В разделе [этой ссылки](https://support.microsoft.com/en-us/kb/2909958/) Дополнительные сведения и примеры для обхода проблемы.|  
|Область|Дополнительный номер|  
|Версия|4.5.1|  
|Тип|Среда выполнения|  
|Анализаторы|CD0130|  
  
<a name="diagnostic131"></a>   
## <a name="131-previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>131: PreviewLostKeyboardFocus вызывается повторно, если соответствующий обработчик показывает окно сообщения Windows Forms  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.5, вызвав `System.Windows.Forms.MessageBox.Show` из `UIElement.PreviewLostKeyboardFocus` обработчика вызовет обработчик повторное срабатывание после закрытия окна сообщения, что может привести к бесконечному циклу окон сообщений.|  
|Предложение|Существует два способа решения этой проблемы —<br /><br /> Его можно избежать путем вызова `System.Windows.MessageBox.Show` вместо `System.Windows.Forms.MessageBox.Show`.<br /><br /> Его можно избежать, отображая окно сообщения с `LostKeyboardFocus` обработчик событий (в отличие от `PreviewLostKeyboardFocus` обработчика событий).|  
|Область|Пограничный случай|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName><br /><br /> <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=fullName>|  
|Анализаторы|CD0131|  
  
<a name="diagnostic133"></a>   
## <a name="133-a-concurrentdictionary-serialized-in-net-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-451-or-452"></a>133: с помощью .NET 4.5.1 или 4.5.2 не может быть десериализован сериализации в .NET 4.5 с NetDataContractSerializer руководство.  
  
|||  
|-|-|  
|Подробные сведения|Из-за изменения внутреннего типа `System.Collections.Concurrent.ConcurrentDictionary` с .NET Framework 4.5 сериализуемых объектов с помощью `NetDataContractSerializer` не может быть десериализован в .NET Framework 4.5.1 или .NET Framework 4.5.2.<br /><br /> Обратите внимание, что перемещение в другом направлении (сериализации в .NET Framework 4.5.x и десериализации с .NET Framework 4.5) работает. Аналогичным образом все сериализации между версиями 4.x работает с .NET Framework 4.6.<br /><br /> Сериализация и десериализация с одной версии платформы .NET Framework не влияет.|  
|Предложение|Если это необходимо для сериализации и десериализации ConcurrentDictionary между .NET Framework 4.5 и .NET Framework 4.5.1/4.5.2, вместо NetDataContractSerializer следует использовать альтернативный сериализатор, как сериализатор DataContractSerializer или BinaryFormatter.<br /><br /> Кроме того поскольку эта проблема решена в .NET Framework 4.6, его можно решить путем обновления до новой версии платформы .NET Framework.|  
|Область|Дополнительный номер|  
|Версия|4.5.1-4.6|  
|Тип|Среда выполнения|  
|Анализаторы|CD0133|  
  
<a name="diagnostic134"></a>   
## <a name="134-persian-calendar-now-uses-the-hijri-solar-algorithm"></a>134: теперь в персидском календаре использует этот алгоритм  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.6, класс PersianCalendar использует алгоритм солнечного календаря хиджры. Преобразование даты между персидского календаря и других календарей может выдать это немного другой результат, начинающаяся с .NET Framework 4.6 для дат позже 2023 гг (по григорианскому календарю) или более ранней, чем 1800.<br /><br /> Кроме того `PersianCalendar.MinSupportedDateTime` теперь `March 22, 0622 instead of March 21, 0622`.|  
|Предложение|Имейте в виду, что некоторые даты рано или поздно могут несколько отличаться при использовании персидского календаря в .NET 4.6. Кроме того при сериализации даты между процессами, которые могут работать на различных версий .NET Framework, не храните их в виде строк дат персидского календаря (поскольку эти значения могут отличаться).|  
|Область|Дополнительный номер|  
|Версия|4.6|  
|Тип|Среда выполнения|  
|Такие API|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|  
|Анализаторы|CD0134|  
  
<a name="diagnostic138"></a>   
## <a name="138-calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>138: вызов метода CreateDefaultAuthorizationContext с аргументом null был изменен  
  
|||  
|-|-|  
|Подробные сведения|Реализация AuthorizationContext возвращается путем вызова `CreateDefaultAuthorizationContext(IList<IAuthorizationPolicy>)` null authorizationPolicies аргумент изменилась реализация в .NET Framework 4.6.|  
|Предложение|В редких случаях в приложениях WCF, которые используют настраиваемую проверку подлинности, могут возникать различия в поведении. В таких случаях можно восстановить прежнее поведение можно двумя способами:<br /><br /> Перекомпилируйте приложение для ориентации на версию .NET Framework, предшествующую 4.6. Для служб, размещенных в IIS, используйте <httpRuntime targetframework="x.x"></httpRuntime> \> элемент на более раннюю версию платформы .NET Framework.<br /><br /> Добавьте следующую строку в `<appSettings>` раздел файла app.config:`<add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />`|  
|Область|Дополнительный номер|  
|Версия|4.6|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29?displayProperty=fullName>|  
|Анализаторы|CD0138|  
  
<a name="diagnostic141"></a>   
## <a name="141-wpf-treeviewitem-must-be-used-within-a-treeview"></a>141: необходимо использовать WPF TreeViewItem в TreeView  
  
|||  
|-|-|  
|Подробные сведения|Изменение было внесено в версии 4.5, который ограничивает использование элементов TreeViewItem за пределами элемента управления TreeView. Это манифесты при следующих условиях:<br /><br /> Визуального родительского элемента TreeViewItem не панель. (TreeViewItem, созданный для элемента управления TreeView будет иметь панель с родительским)<br /><br /> TreeViewItem является потомком VirtualizingStackPanel выступает в качестве «элементы узла» для элемента управления "список" (ListBox, DataGrid, ListView, и т. д.). Виртуализация не обязательно должно быть включено.<br /><br /> VirtualizingStackPanel прокрутки элемента (`ScrollUnit="Item"`).<br /><br /> Кто-то звонит `VirtualizingStackPanel.MakeVisible(v)` для прокрутки элемента `v` в представление. Это можно сделать явно или неявно несколькими способами; Возможно самым распространенным способом достаточно щелкнуть `v` отказаться от нее фокус.<br /><br /> Visual родительской цепочке от `v` к VirtualizingStackPanel, проходит через TreeViewItem.<br /><br /> Другими словами это происходит в том случае TreeViewItem используется вне элемента управления TreeView и пользователь щелкает потомком TreeViewItem, чтобы сделать его видимым. Если TreeViewItem не имеющий фокус потомков, вы никогда не увидите эту проблему. Пример ситуации, когда будет достигнута при TreeViewItem является корнем DataTemplate.  При достижении этой проблемы существует исключение InvalidCastException, происходит в рамках платформы WPF.|  
|Предложение|Исправление будут доступны для этого.|  
|Область|Дополнительный номер|  
|Версия|4.5|  
|Тип|Среда выполнения|  
|Анализаторы|CD0141|  
  
<a name="diagnostic143"></a>   
## <a name="143-x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>143: X509CertificateClaimSet.FindClaims рассматривает все claimTypes.  
  
|||  
|-|-|  
|Подробные сведения|В приложениях, предназначенных для .NET Framework 4.6.1, если X509 набор утверждений инициализируется из сертификат, который содержит несколько записей DNS его SAN, в метод FindClaims пытается сопоставить аргумент claimType с DNS-записей.<br /><br /> Для приложений, предназначенных для предыдущих версий платформы .NET Framework метод FindClaims предпринимает попытку сопоставить аргумент claimType только с последней записи DNS.|  
|Предложение|Это изменение влияет только на приложения, предназначенные для .NET Framework 4.6.1. Это изменение может быть отключена (или если для различных версий pre-4.6.1) с [DisableMultipleDNSEntries](https://msdn.microsoft.com/en-us/library/mt620030%28v=vs.110%29.aspx) переключатель совместимости.|  
|Область|Дополнительный номер|  
|Версия|4.6.1|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%28System.String%2CSystem.String%29?displayProperty=fullName>|  
|Анализаторы|CD0143|  
  
<a name="diagnostic144"></a>   
## <a name="144-applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>144: Application.FilterMessage больше не создает исключение для реентерабельным реализаций IMessageFilter.PreFilterMessage  
  
|||  
|-|-|  
|Подробные сведения|До .NET Framework 4.6.1 вызова Application.FilterMessage с IMessageFilter.PreFilterMessage каким именем AddMessageFilter или RemoveMessageFilter (в ходе также вызова Application.DoEvents) приведет к IndexOutOfRangeException.<br /><br /> Начиная с приложений, предназначенных для .NET Framework 4.6.1, это исключение не создается, и фильтры реентерабельным описанным выше могут быть использованы.|  
|Предложение|Имейте в виду, что Application.FilterMessage больше не будет генерировать для реентерабельным IMessageFilter.PreFilterMessage поведение, описанное выше. Это влияет только на приложения, предназначенные для .NET Framework 4.6.1.<br /><br /> Приложения, предназначенные для .NET Framework 4.6.1 можно отказаться от этого изменения (или может включить нацеливания на более старых платформ приложений) с помощью [DontSupportReentrantFilterMessage](https://msdn.microsoft.com/en-us/library/mt620032%28v=vs.110%29.aspx) переключатель совместимости.|  
|Область|Пограничный случай|  
|Версия|4.6.1|  
|Тип|Изменение целевой платформы|  
|Такие API|<xref:System.Windows.Forms.Application.FilterMessage%28System.Windows.Forms.Message%40%29?displayProperty=fullName>|  
|Анализаторы|CD0144|  
  
<a name="diagnostic145"></a>   
## <a name="145-currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>145: CurrentCulture не сохранено в рамках операции диспетчер WPF  
  
|||  
|-|-|  
|Подробные сведения|Начиная с .NET Framework 4.6, CurrentCulture и CurrentUICulture изменения в [диспетчер](https://msdn.microsoft.com/en-us/library/system.windows.threading.dispatcher%28v=vs.110%29.aspx) будут утеряны в конце операции dispatcher. Аналогичным образом изменения CurrentCulture и CurrentUICulture, сделанные за пределами операции диспетчер могут не отображаться при том, что операция выполняется.<br /><br /> Проще говоря, это означает, что изменения CurrentCulture и CurrentUICulture может не обмениваются пользовательского интерфейса WPF обратные вызовы и другой код в приложении WPF.<br /><br /> Это происходит из-за изменений в [ExecutionContext](https://msdn.microsoft.com/en-us/library/system.threading.executioncontext%28v=vs.110%29.aspx) , вызывающий CurrentCulture и CurrentUICulture хранится в контекст выполнения, начиная с приложений, предназначенных для .NET Framework 4.6. WPF диспетчера операций сохранить контекст выполнения, который используется для запуска операции и восстановление предыдущего контекста при завершении операции. Поскольку CurrentCulture и CurrentUICulture теперь являются частью этого контекста, изменения их в рамках операции диспетчер не сохраняются за пределами операции.|  
|Предложение|Приложения, которые затрагивает данное изменение может обойти, сохраняя требуемый CurrentCulture и CurrentUICulture в поле и возвращать все операции диспетчер институтов (включая обработчики обратный вызов пользовательского интерфейса) задайте правильный CurrentCulture и CurrentUICulture. Кроме того поскольку ExecutionContext изменить базовый WPF изменение влияет только на приложения, предназначенные для .NET Framework 4.6 или более поздней версии, этот разрыв можно избежать, предназначенные для .NET Framework 4.5.2.|  
|Область|Дополнительный номер|  
|Версия|4.6|  
|Тип|Изменение целевой платформы|  
|Анализаторы|CD0145|