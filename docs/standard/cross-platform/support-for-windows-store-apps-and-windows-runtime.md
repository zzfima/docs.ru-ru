---
title: Поддержка приложений для Магазина Windows и среды выполнения Windows в .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Windows Store apps, .NET Framework support for
- Windows Runtime, .NET Framework support for
- .NET for Windows Store apps
- .NET Framework, and Windows Store apps
- .NET Framework, and Windows Runtime
ms.assetid: 6fa7d044-ae12-4c54-b8ee-50915607a565
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c49e9a5c4b8785704f8c4cbd1c9b7af10dc0c689
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661785"
---
# <a name="net-framework-support-for-windows-store-apps-and-windows-runtime"></a>Поддержка приложений для Магазина Windows и среды выполнения Windows в .NET Framework

.NET Framework 4.5 поддерживает ряд сценариев разработки программного обеспечения в среде выполнения Windows. Эти способы можно разделить на три категории.

- Разработка [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложений с помощью элементов управления XAML, как описано в разделе [приложений стратегии для Windows Store, с помощью C# или Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10)), [как tos (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10)), и [Обзор приложений .NET для Windows Store ](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)).

- Разработка библиотек классов для использования в приложениях [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], создаваемых с помощью .NET Framework.

- Разработка компонентов среды выполнения Windows, упакованные в. Файлы WinMD, которые можно использовать в любом языке программирования, поддерживающий среду выполнения Windows. Например, см. в разделе [создание компонентов среды выполнения Windows на C# и Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

В этом разделе описывается поддержка, что платформа .NET Framework предоставляет для всех трех категорий и описываются сценарии для компонентов среды выполнения Windows. Первый раздел содержит базовые сведения о связи между .NET Framework и среды выполнения Windows и объясняется некоторые странности, с которыми можно столкнуться в системе справки и интегрированной среды разработки. [Второй раздел](#WindowsRuntimeComponents) описываются сценарии разработки компонентов среды выполнения Windows.

## <a name="the-basics"></a>Основы

Платформа .NET Framework поддерживает три сценария разработки перечисленных ранее, предоставляя [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]и за счет поддержки самой среде выполнения Windows.

- [Пространства имен .NET framework и среды выполнения Windows](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)#net-framework-and-windows-runtime-namespaces) обеспечивает удобное представление библиотек классов .NET Framework и перечислением только тех типов и членов, которые можно использовать для создания [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения и компоненты среды выполнения Windows.

  - При использовании Visual Studio (Visual Studio 2012 или более поздней версии) для разработки [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложение или компонент среды выполнения Windows, набор базовых сборок гарантирует, что вы видите только соответствующие типы и члены.

  - Этот оптимизированный набор API упрощен путем удаления компонентов, которые дублированы .NET Framework или дублируют среды выполнения Windows функции. Например, он содержит только уникурсальные версии типов коллекций, и объектной модели документов XML исключается пользу XML API среды выполнения Windows задайте.

  - Функции, которые просто являются оболочками системного API, также удаляются, так как позволяет легко вызывать из управляемого кода среда выполнения Windows.

  Дополнительные сведения о [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], см. в разделе [Обзор приложений .NET для Windows Store](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). Чтобы прочитать о процессе выбора API, см. в разделе [.NET для приложений в стиле Metro](https://devblogs.microsoft.com/dotnet/net-for-metro-style-apps/) запись в блоге .NET.

- [Среды выполнения Windows](/uwp/api/) предоставляет элементы интерфейса пользователя для создания [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения и предоставляет доступ к функциям операционной системы. Как и .NET Framework, среда выполнения Windows имеет метаданные, которые позволяют C# и библиотеки классов Visual Basic компиляторы для использования среды выполнения Windows, способ работы в .NET Framework. Платформа .NET Framework упрощает использование среды выполнения Windows, скрывая некоторые различия:

  - Некоторые отличия в шаблонах .NET Framework и среды выполнения Windows, таких как шаблон для добавления и удаления обработчиков событий, программирования, скрыты. Можно просто использовать шаблон .NET Framework.

  - Некоторые отличия часто используемых типов (например, примитивных типов и коллекций) также скрыты. Просто используйте тип .NET Framework, как описано в [различия, которые видимы в интегрированной среде разработки](#DifferencesVisibleInIDE)далее в этой статье.

В большинстве случаев, поддержка среды выполнения Windows в .NET Framework является прозрачным. В следующем разделе рассматриваются некоторые значимые различия между управляемым кодом и среда выполнения Windows.

<a name="AboutReferenceDocumentation"></a>

### <a name="the-net-framework-and-the-windows-runtime-reference-documentation"></a>.NET Framework и документацию на среды выполнения Windows

Среда выполнения Windows и наборы документации .NET Framework отделены друг с другом. При нажатии клавиши F1 для отображения справки для типа или члена отображается справочная документация из соответствующего набора. Тем не менее при просмотре [на среды выполнения Windows](/uwp/api/) можно столкнуться с непонятными примерами:

- Разделы, такие как <xref:Windows.Foundation.Collections.IIterable%601> интерфейса не имеют синтаксиса объявления для Visual Basic или C#. Вместо этого над разделом синтаксиса отображается Примечание (в данном случае «.NET: Этот интерфейс отображается как System.Collections.Generic.IEnumerable\<T >»). Это так, как .NET Framework и среды выполнения Windows предоставляют аналогичные функциональные возможности с помощью различных интерфейсов. Кроме того, существуют отличия в поведении: `IIterable` содержит метод `First` вместо метода <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> для возврата перечислителя. Чтобы вам не приходилось использовать другой способ для выполнения типичных задач, платформа .NET Framework поддерживает среды выполнения Windows, сделав управляемый код для использования типа должны быть знакомы с. Вы не увидите `IIterable` интерфейса в интегрированной среде разработки, и поэтому единственным способом, вам придется столкнуться в справочной документации среды выполнения Windows является путем просмотра непосредственно из этой документации.

- <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)> Документации иллюстрирует сходная ситуация: Его типы параметров различаются для разных языков. Для C# и Visual Basic типами параметров являются <xref:System.String?displayProperty=nameWithType> и <xref:System.Uri?displayProperty=nameWithType>. Это происходит потому, что платформа .NET Framework имеет собственные типы `String` и `Uri`, и для таких часто используемых типов не имеет смысла принуждать пользователей .NET Framework использовать другой способ выполнения действий. В Интегрированной среде разработки .NET Framework скрывает соответствующие типы среды выполнения Windows.

- В некоторых случаях таких как <xref:Windows.UI.Xaml.GridLength> структуры, .NET Framework предоставляет тип с тем же именем, но дополнительные функциональные возможности. Например, разделы о конструкторе и свойствах связаны с `GridLength`, но они имеют блоков синтаксиса только для Visual Basic и C#, так как эти члены доступны только в управляемом коде. В среде выполнения Windows структуры имеют только поля. Структура среды выполнения Windows необходим вспомогательный класс, <xref:Windows.UI.Xaml.GridLengthHelper>, чтобы обеспечить аналогичные функции. Вы не увидите этот вспомогательный класс в интегрированной среде разработки при создании управляемого кода.

- В интегрированной среде разработки, типы среды выполнения Windows представляются являются производными от <xref:System.Object?displayProperty=nameWithType>. У них могут быть члены, унаследованные от <xref:System.Object>, например <xref:System.Object.ToString%2A?displayProperty=nameWithType>. Эти члены работают, как если бы, если напрямую унаследованы от <xref:System.Object>, и типов среды выполнения Windows может быть приведен к <xref:System.Object>. Эта функция является частью возможностей .NET Framework для среды выполнения Windows. Тем не менее если типы в справочной документации среды выполнения Windows, такие элементы не отображаются. Документация для этих унаследованных членов предоставляется в документации по <xref:System.Object?displayProperty=nameWithType>.

<a name="DifferencesVisibleInIDE"></a>

### <a name="differences-that-are-visible-in-the-ide"></a>Различия, которые видимы в интегрированной среде разработки

В более сложных сценариях программирования, например с помощью компонента среды выполнения Windows, написанных на C# для создания приложения логики для [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения, созданного для Windows, с помощью JavaScript, подобные различия видны как в интегрированной среде разработки также как и в документация. Когда компонент возвращает `IDictionary<int, string>` JavaScript, и посмотреть его в отладчике JavaScript, вы увидите методы `IMap<int, string>` так, как в коде JavaScript используется тип среды выполнения Windows. Несколько часто используемых типов коллекций, которые по-разному представляются в этих двух языках, показаны в следующей таблице.

|Тип среды выполнения Windows|Соответствующий тип платформы .NET Framework|
|--------------------------------------------------------------|---------------------------------------|
|`IIterable<T>`|`IEnumerable<T>`|
|`IIterator<T>`|`IEnumerator<T>`|
|`IVector<T>`|`IList<T>`|
|`IVectorView<T>`|`IReadOnlyList<T>`|
|`IMap<K, V>`|`IDictionary<TKey, TValue>`|
|`IMapView<K, V>`|`IReadOnlyDictionary<TKey, TValue>`|
|`IBindableIterable`|`IEnumerable`|
|`IBindableVector`|`IList`|
|`Windows.UI.Xaml.Data.INotifyPropertyChanged`|`System.ComponentModel.INotifyPropertyChanged`|
|`Windows.UI.Xaml.Data.PropertyChangedEventHandler`|`System.ComponentModel.PropertyChangedEventHandler`|
|`Windows.UI.Xaml.Data.PropertyChangedEventArgs`|`System.ComponentModel.PropertyChangedEventArgs`|

В среде выполнения Windows `IMap<K, V>` и `IMapView<K, V>` осуществляется итерация с помощью `IKeyValuePair`. При передаче этих типов в управляемый код они представляются как `IDictionary<TKey, TValue>` и `IReadOnlyDictionary<TKey, TValue>`, поэтому для их перебора можно обычным образом использовать `System.Collections.Generic.KeyValuePair<TKey, TValue>`.

Представление интерфейсов в управляемом коде влияет на представление типов, реализующих эти интерфейсы. Например, класс `PropertySet` реализует `IMap<K, V>`, который представлен в управляемом коде как `IDictionary<TKey, TValue>`. `PropertySet` представляет себя как реализующего `IDictionary<TKey, TValue>` вместо `IMap<K, V>`, поэтому в управляемом коде у него присутствует метод `Add`, который ведет себя как метод `Add` в словарях .NET Framework. А метода `Insert` у этого типа нет.

Дополнительные сведения об использовании платформы .NET Framework для создания в компонент среды выполнения Windows и пошаговое руководство, в котором демонстрируется использование этого компонента с JavaScript см. в разделе [создание компонентов среды выполнения Windows в C# и Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

### <a name="primitive-types"></a>Типы-примитивы

Чтобы включить естественное использование среды выполнения Windows в управляемом коде, вместо простых типов среды выполнения Windows в коде отображаются простые типы .NET Framework. В .NET Framework у простых типов, таких как структура `Int32`, имеется множество полезных свойств и методов, например метод `Int32.TryParse`. Напротив простые типы и структуры в среде выполнения Windows имеют только поля. При использовании простых типов в управляемом коде они представляются как типы платформы .NET Framework, и можно как обычно использовать свойства и методы типов платформы .NET Framework. В следующем списке приводятся сводные данные.

- Для среды выполнения Windows примитивов `Int32`, `Int64`, `Single`, `Double`, `Boolean`, `String` (постоянную коллекцию символов Юникода), `Enum`, `UInt32`, `UInt64`, и `Guid`, используйте тип с тем же именем в `System` пространства имен.

- вместо `UInt8` используется тип `System.Byte`;

- вместо `Char16` используется тип `System.Char`;

- вместо интерфейса `IInspectable` используется тип `System.Object`.

- Для `HRESULT` используйте структуру с одним членом `System.Int32`.

Как и в типы интерфейсов, единственный случай, может появиться это представление является, когда проект платформы .NET Framework в компонент среды выполнения Windows, которая используется [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения, созданного с использованием JavaScript.

Другие типы среды выполнения Windows основные, часто используемом, которые отображаются в управляемом коде в качестве эквивалентов из .NET Framework включают `Windows.Foundation.DateTime` структуру, которая отображается в управляемом коде как <xref:System.DateTimeOffset?displayProperty=nameWithType> структуры и `Windows.Foundation.TimeSpan` структуры, который отображается в виде <xref:System.TimeSpan?displayProperty=nameWithType> структуры.

### <a name="other-differences"></a>Другие различия

В некоторых случаях тот факт, что типы .NET Framework, отображаются в коде вместо типов среды выполнения Windows требует действий со стороны пользователя. Например <xref:Windows.Foundation.Uri?displayProperty=nameWithType> класс отображается как <xref:System.Uri?displayProperty=nameWithType> в коде .NET Framework. <xref:System.Uri?displayProperty=nameWithType> Разрешает относительный URI, но <xref:Windows.Foundation.Uri?displayProperty=nameWithType> необходим абсолютный URI. Таким образом при передаче URI в метод среды выполнения Windows, необходимо убедиться, что он является абсолютным. (См. в разделе [передача URI в среду выполнения Windows](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md).)

<a name="WindowsRuntimeComponents"></a>

## <a name="scenarios-for-developing-windows-runtime-components"></a>Сценарии для разработки компонентов среды выполнения Windows

Сценарии, которые поддерживаются для управляемых компонентов среды выполнения Windows зависят от следующих общих принципов:

- Компоненты среды выполнения Windows, созданных с помощью .NET Framework не имеют явных отличий от других Runtimelibraries Windows. Например если вы повторно реализовать собственный компонент среды выполнения Windows с помощью управляемого кода, эти два компонента, внешне неотличимы. Дело в том, что компонент, написанный в управляемом коде, остается незаметным для кода, который его использует, даже если сам код является управляемым. Однако на внутреннем уровне компонент является настоящим управляемым кодом и работает в среде CLR.

- Компоненты могут содержать типы, реализующие логику приложения, элементы управления пользовательского интерфейса [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] или и те, и другие.

  > [!NOTE]
  > Рекомендуется отделять элементы пользовательского интерфейса от логики приложения. Кроме того, нельзя использовать элементы управления пользовательского интерфейса [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] в приложении [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], созданном для Windows с помощью JavaScript и HTML.

- Компонент может быть проектом внутри решения Visual Studio для приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] или многоразовым компонентом, который можно добавить к нескольким решениям.

  > [!NOTE]
  > Если компонент будет использоваться только с C# или Visual Basic, нет причин делать его в компонент среды выполнения Windows. Если сделать его обычной библиотеки классов .NET Framework вместо этого, у вас нет для ограничения его поверхности открытого API типами среды выполнения Windows.

- Версии повторно используемых компонентов можно выпускать с использованием среды Windows <xref:Windows.Foundation.Metadata.VersionAttribute> атрибут, чтобы определить, какие типы (и какие члены типа) добавлены в другой версии.

- Типы в компоненте можно получить из типов среды выполнения Windows. Элементы управления могут наследовать от простых типов элементов управления в <xref:Windows.UI.Xaml.Controls.Primitives> пространства имен или от более оформленных элементов управления, такие как <xref:Windows.UI.Xaml.Controls.Button>.

  > [!IMPORTANT]
  > Начиная с [!INCLUDE[win8](../../../includes/win8-md.md)] и .NET Framework 4.5, все открытые типы в управляемого компонента среды выполнения Windows должен быть запечатан. Тип в другом компоненте среды выполнения Windows не может быть производным от них. Если необходимо предоставить полиморфное расширения функциональности в компоненте, можно создать интерфейс и реализовать его в полиморфных типах.

- Все типы параметров и возвращаемого значения открытых типов в компоненте должны быть типы среды выполнения Windows (включая типы среды выполнения Windows, которые определяет компонент).

Следующие разделы содержат примеры распространенных сценариев.

### <a name="application-logic-for-a-includewin8appnamelongincludeswin8-appname-long-mdmd-app-with-javascript"></a>Логика приложения для приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] с JavaScript

При создании приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] для Windows с помощью JavaScript может оказаться, что некоторые части логики приложения работают лучше в управляемом коде или их легче так разработать. Javascript не может использовать библиотеки классов платформы .NET Framework непосредственно, но можно сделать библиотекой классов файл .WinMD. В этом случае компонент среды выполнения Windows является неотъемлемой частью приложения, поэтому нет смысла указывать атрибуты версии.

### <a name="reusable-includewin8appnamelongincludeswin8-appname-long-mdmd-ui-controls"></a>Повторно используемые элементы управления пользовательского интерфейса [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]

Можно упаковать набор связанных элементов управления пользовательского интерфейса в повторно используемый компонент среды выполнения Windows. Компонент может распространяться сам по себе или использоваться как элемент в приложениях, которые вы создаете. В этом случае имеет смысл использовать среду выполнения Windows <xref:Windows.Foundation.Metadata.VersionAttribute> атрибут для улучшения совместимости.

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>Логика приложения с возможностью повторного использования существующих приложений платформы .NET Framework

Можно упаковать управляемый код из существующих классических приложений в виде отдельного компонента среды выполнения Windows. Это позволит использовать его в приложениях [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], созданных с помощью C++ или JavaScript, а также в приложениях [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], созданных с помощью C# или Visual Basic. Используйте управление версиями, если этот код будет использоваться в нескольких местах.

## <a name="related-topics"></a>См. также

|Заголовок|Описание|
|-----------|-----------------|
|[Общие сведения о платформе .NET для приложений Магазина Windows](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))|Описывает типы .NET Framework и члены, которые можно использовать для создания [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения и Windows RuntimeComponents. (В Центре разработки для Windows.)|
|[Схема создания приложений Windows Store, с помощью C# или Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10))|Предоставляет основные ресурсы, помогающие начать разрабатывать приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] с помощью C# или Visual Basic, а также многие разделы краткого руководства, правила и рекомендации. (В Центре разработки для Windows.)|
|[Как и инструкции (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))|Предоставляет основные ресурсы, помогающие начать разрабатывать приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] с помощью C# или Visual Basic, а также многие разделы краткого руководства, правила и рекомендации. (В Центре разработки для Windows.)|
|[Создание компонентов среды выполнения Windows в C# и Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|Описывает создание компонента среды выполнения Windows с помощью .NET Framework, объясняет, как использовать его как часть [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения для Windows, с помощью JavaScript и способы отладки в сочетании с Visual Studio. (В Центре разработки для Windows.)|
|[Ссылка на среды выполнения Windows](/uwp/api/)|Справочная документация для среды выполнения Windows. (В Центре разработки для Windows.)|
|[Передача URI в среду выполнения Windows](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)|Описание проблемы, которые могут возникнуть при передаче URI из управляемого кода для среды выполнения Windows и как этого избежать.|
