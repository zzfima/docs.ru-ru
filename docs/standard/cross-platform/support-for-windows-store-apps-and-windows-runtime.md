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
ms.openlocfilehash: c2870e79d82d92bd0c853e6e042add3b4243f888
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835490"
---
# <a name="net-framework-support-for-windows-store-apps-and-windows-runtime"></a>Поддержка приложений для Магазина Windows и среды выполнения Windows в .NET Framework

  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] поддерживает несколько способов разработки программного обеспечения для [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Эти способы можно разделить на три категории.

-   Разработка [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложений с помощью элементов управления XAML, как описано в разделе [приложений стратегии для Windows Store, с помощью C# или Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10)), [как tos (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10)), и [Обзор приложений .NET для Windows Store ](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)).

-   Разработка библиотек классов для использования в приложениях [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], создаваемых с помощью .NET Framework.

-   Разработка компонентов [!INCLUDE[wrt](../../../includes/wrt-md.md)], упакованных в файлы WinMD, которые можно использовать в любом языке программирования, поддерживающем [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Например, см. в разделе [создание компонентов среды выполнения Windows на C# и Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

 В этом разделе кратко описана поддержка, которую платформа .NET Framework предоставляет для всех трех категорий, и описываются сценарии для компонентов [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Первый раздел содержит основные сведения о связи между .NET Framework и [!INCLUDE[wrt](../../../includes/wrt-md.md)], и рассматривает некоторые странности, с которыми вы можете столкнуться в системе справки и интегрированной среды разработки. [Второй раздел](#WindowsRuntimeComponents) описываются сценарии разработки [!INCLUDE[wrt](../../../includes/wrt-md.md)] компонентов.

## <a name="the-basics"></a>Основы
 Платформа .NET Framework поддерживает три сценария разработки, перечисленных ранее, предоставляя [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] и за счет поддержки самой [!INCLUDE[wrt](../../../includes/wrt-md.md)].

-   [Пространства имен .NET framework и среды выполнения Windows](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)#net-framework-and-windows-runtime-namespaces) обеспечивает удобное представление библиотек классов .NET Framework и перечислением только тех типов и членов, которые можно использовать для создания [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложений и [!INCLUDE[wrt](../../../includes/wrt-md.md)] компонентов.

    -   При использовании Visual Studio (Visual Studio 2012 или более поздней версии) для разработки [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения или [!INCLUDE[wrt](../../../includes/wrt-md.md)] компонента, набор базовых сборок гарантирует, что вы видите только соответствующие типы и члены.

    -   Этот оптимизированный набор API также упрощен за счет удаления функций, которые дублированы на платформе .NET Framework или дублируют функции [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Например, он содержит только уникурсальные версии типов коллекций, а объектная модель XML-документа исключена в пользу набора API XML [!INCLUDE[wrt](../../../includes/wrt-md.md)].

    -   Функции, которые просто являются оболочками системного API, также удалены, поскольку функции [!INCLUDE[wrt](../../../includes/wrt-md.md)] просто вызываются из управляемого кода.

     Дополнительные сведения о [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], см. в разделе [Обзор приложений .NET для Windows Store](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). Чтобы прочитать о процессе выбора API, см. в разделе [.NET для приложений в стиле Metro](https://blogs.msdn.microsoft.com/dotnet/2012/04/17/net-for-metro-style-apps/) запись в блоге .NET.

-   [Среды выполнения Windows](/uwp/api/) предоставляет элементы интерфейса пользователя для создания [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения и предоставляет доступ к функциям операционной системы. Как и платформа .NET Framework, [!INCLUDE[wrt](../../../includes/wrt-md.md)] содержит метаданные, которые позволяют компиляторам C# и Visual Basic использовать [!INCLUDE[wrt](../../../includes/wrt-md.md)] так же, как они используют библиотеки классов платформы .NET Framework. Платформа .NET Framework упрощает использование [!INCLUDE[wrt](../../../includes/wrt-md.md)], скрывая некоторые различия:

    -   Некоторые отличия в шаблонах программирования для платформы .NET Framework и [!INCLUDE[wrt](../../../includes/wrt-md.md)], например шаблон добавления и удаления обработчиков событий, скрыты. Можно просто использовать шаблон .NET Framework.

    -   Некоторые отличия часто используемых типов (например, примитивных типов и коллекций) также скрыты. Просто используйте тип .NET Framework, как описано в [различия, которые видимы в интегрированной среде разработки](#DifferencesVisibleInIDE)далее в этой статье.

 Большую часть времени поддержка платформы .NET Framework для [!INCLUDE[wrt](../../../includes/wrt-md.md)] происходит прозрачно. В следующем разделе описываются некоторые значимые различия между управляемым кодом и [!INCLUDE[wrt](../../../includes/wrt-md.md)].

<a name="AboutReferenceDocumentation"></a>
### <a name="the-net-framework-and-the-includewrtincludeswrt-mdmd-reference-documentation"></a>Справочная документация по платформе .NET Framework и [!INCLUDE[wrt](../../../includes/wrt-md.md)]
 Среда выполнения Windows и наборы документации .NET Framework отделены друг с другом. При нажатии клавиши F1 для отображения справки для типа или члена отображается справочная документация из соответствующего набора. Тем не менее при просмотре [на среды выполнения Windows](/uwp/api/) можно столкнуться с непонятными примерами:

-   Разделы, такие как <xref:Windows.Foundation.Collections.IIterable%601> интерфейса не имеют синтаксиса объявления для Visual Basic или C#. Вместо этого над разделом синтаксиса отображается Примечание (в данном случае «.NET: Этот интерфейс отображается как System.Collections.Generic.IEnumerable\<T >»). Это происходит потому, что платформа .NET Framework и [!INCLUDE[wrt](../../../includes/wrt-md.md)] обеспечивают одну и ту же функциональность с помощью различных интерфейсов. Кроме того, существуют отличия в поведении: `IIterable` содержит метод `First` вместо метода <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> для возврата перечислителя. Вместо необходимости изучать другой способ выполнения типичных задач, платформа .NET Framework поддерживает [!INCLUDE[wrt](../../../includes/wrt-md.md)], из-за чего создается видимость, что управляемый код использует знакомый вам тип. Вы не увидите интерфейс `IIterable` в интегрированной среде разработки и поэтому можете встретить его в справочной документации по [!INCLUDE[wrt](../../../includes/wrt-md.md)], только просматривая эту документацию непосредственно.

-   <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)> Документации иллюстрирует сходная ситуация: Его типы параметров различаются для разных языков. Для C# и Visual Basic типами параметров являются <xref:System.String?displayProperty=nameWithType> и <xref:System.Uri?displayProperty=nameWithType>. Это происходит потому, что платформа .NET Framework имеет собственные типы `String` и `Uri`, и для таких часто используемых типов не имеет смысла принуждать пользователей .NET Framework использовать другой способ выполнения действий. В интегрированной среде разработки платформа .NET Framework скрывает соответствующие типы [!INCLUDE[wrt](../../../includes/wrt-md.md)].

-   В некоторых случаях таких как <xref:Windows.UI.Xaml.GridLength> структуры, .NET Framework предоставляет тип с тем же именем, но дополнительные функциональные возможности. Например, разделы о конструкторе и свойствах связаны с `GridLength`, но они имеют блоков синтаксиса только для Visual Basic и C#, так как эти члены доступны только в управляемом коде. В [!INCLUDE[wrt](../../../includes/wrt-md.md)] структуры имеют только поля. [!INCLUDE[wrt](../../../includes/wrt-md.md)] Структуры необходим вспомогательный класс, <xref:Windows.UI.Xaml.GridLengthHelper>, чтобы обеспечить аналогичные функции. Вы не увидите этот вспомогательный класс в интегрированной среде разработки при создании управляемого кода.

-   В интегрированной среде разработки типы [!INCLUDE[wrt](../../../includes/wrt-md.md)], по-видимому, являются производными от <xref:System.Object?displayProperty=nameWithType>. У них могут быть члены, унаследованные от <xref:System.Object>, например <xref:System.Object.ToString%2A?displayProperty=nameWithType>. Эти члены работают так, как если бы они были напрямую унаследованы от <xref:System.Object>. В [!INCLUDE[wrt](../../../includes/wrt-md.md)] типы могут быть приведены к <xref:System.Object>. Эта функциональность является частью поддержки, которую платформа .NET Framework предоставляет для [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Однако при просмотре типов в справочной документации по [!INCLUDE[wrt](../../../includes/wrt-md.md)] такие элементы не отображаются. Документация для этих унаследованных членов предоставляется в документации по <xref:System.Object?displayProperty=nameWithType>.

<a name="DifferencesVisibleInIDE"></a>
### <a name="differences-that-are-visible-in-the-ide"></a>Различия, которые видимы в интегрированной среде разработки
 В более сложных сценариях программирования, например с использованием компонента [!INCLUDE[wrt](../../../includes/wrt-md.md)], написанного на C#, для предоставления логики приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], созданного для Windows с помощью JavaScript, подобные различия четко видны как в интегрированной среде разработки, так и в документации. Если в тот момент, когда компонент возвращает `IDictionary<int, string>` в JavaScript, посмотреть его в отладчике JavaScript, можно увидеть методы `IMap<int, string>`, поскольку JavaScript использует тип [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Несколько часто используемых типов коллекций, которые по-разному представляются в этих двух языках, показаны в следующей таблице.

|Тип [!INCLUDE[wrt](../../../includes/wrt-md.md)]|Соответствующий тип платформы .NET Framework|
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

 В [!INCLUDE[wrt](../../../includes/wrt-md.md)] по `IMap<K, V>` и `IMapView<K, V>` осуществляется итерация с помощью `IKeyValuePair`. При передаче этих типов в управляемый код они представляются как `IDictionary<TKey, TValue>` и `IReadOnlyDictionary<TKey, TValue>`, поэтому для их перебора можно обычным образом использовать `System.Collections.Generic.KeyValuePair<TKey, TValue>`.

 Представление интерфейсов в управляемом коде влияет на представление типов, реализующих эти интерфейсы. Например, класс `PropertySet` реализует `IMap<K, V>`, который представлен в управляемом коде как `IDictionary<TKey, TValue>`. `PropertySet` представляет себя как реализующего `IDictionary<TKey, TValue>` вместо `IMap<K, V>`, поэтому в управляемом коде у него присутствует метод `Add`, который ведет себя как метод `Add` в словарях .NET Framework. А метода `Insert` у этого типа нет.

 Дополнительные сведения об использовании платформы .NET Framework для создания [!INCLUDE[wrt](../../../includes/wrt-md.md)] компонента и пошаговое руководство, которое демонстрирует использование этого компонента с JavaScript, см. в разделе [создание компонентов среды выполнения Windows на C# и Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

### <a name="primitive-types"></a>Типы-примитивы
 Для удобного использования [!INCLUDE[wrt](../../../includes/wrt-md.md)] в управляемом коде вместо простых типов [!INCLUDE[wrt](../../../includes/wrt-md.md)] в коде отображаются простые типы платформы .NET Framework. В .NET Framework у простых типов, таких как структура `Int32`, имеется множество полезных свойств и методов, например метод `Int32.TryParse`. Напротив, простые типы и структуры в [!INCLUDE[wrt](../../../includes/wrt-md.md)] имеют только поля. При использовании простых типов в управляемом коде они представляются как типы платформы .NET Framework, и можно как обычно использовать свойства и методы типов платформы .NET Framework. В следующем списке приводятся сводные данные.

-   вместо простых типов [!INCLUDE[wrt](../../../includes/wrt-md.md)]`Int32`, `Int64`, `Single`, `Double`, `Boolean`, `String` (неизменяемая коллекция символов Юникода), `Enum`, `UInt32`, `UInt64` и `Guid` используются одноименные типы из пространства имен `System`;

-   вместо `UInt8` используется тип `System.Byte`;

-   вместо `Char16` используется тип `System.Char`;

-   вместо интерфейса `IInspectable` используется тип `System.Object`.

-   Для `HRESULT` используйте структуру с одним членом `System.Int32`.

 Как и в случае с типами интерфейса, единственным случаем, когда можно увидеть это представление, является случай, когда проект платформы .NET Framework является компонентом [!INCLUDE[wrt](../../../includes/wrt-md.md)], который используется приложением [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], построенным с помощью JavaScript.

 В число других часто используемых типов [!INCLUDE[wrt](../../../includes/wrt-md.md)], которые появляются в управляемом коде в качестве своих эквивалентов на платформе .NET Framework, включают в себя структуру `Windows.Foundation.DateTime`, которая отображается в управляемом коде в виде структуры <xref:System.DateTimeOffset?displayProperty=nameWithType>, и структуру `Windows.Foundation.TimeSpan`, которая отображается в виде структуры <xref:System.TimeSpan?displayProperty=nameWithType>.

### <a name="other-differences"></a>Другие различия
 В некоторых случаях тот факт, что типы .NET Framework отображаются в коде вместо типов [!INCLUDE[wrt](../../../includes/wrt-md.md)], требует вмешательства со стороны пользователя. Например <xref:Windows.Foundation.Uri?displayProperty=nameWithType> класс отображается как <xref:System.Uri?displayProperty=nameWithType> в коде .NET Framework. <xref:System.Uri?displayProperty=nameWithType> Разрешает относительный URI, но <xref:Windows.Foundation.Uri?displayProperty=nameWithType> необходим абсолютный URI. Таким образом, при передаче URI методу [!INCLUDE[wrt](../../../includes/wrt-md.md)] необходимо убедиться, что он является абсолютным. (См. в разделе [передача URI в среду выполнения Windows](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md).)

<a name="WindowsRuntimeComponents"></a>
## <a name="scenarios-for-developing-windows-runtime-components"></a>Сценарии для разработки компонентов среды выполнения Windows
 Сценарии, поддерживаемые для управляемых компонентов [!INCLUDE[wrt](../../../includes/wrt-md.md)], зависят от следующих общих принципов.

-   Компоненты [!INCLUDE[wrt](../../../includes/wrt-md.md)], созданные с использованием платформы .NET Framework, не имеют явных отличий от других библиотек [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Например, если реализовать собственный компонент [!INCLUDE[wrt](../../../includes/wrt-md.md)] еще раз с помощью управляемого кода, получившиеся компоненты для использующего их кода будут неразличимы. Дело в том, что компонент, написанный в управляемом коде, остается незаметным для кода, который его использует, даже если сам код является управляемым. Однако на внутреннем уровне компонент является настоящим управляемым кодом и работает в среде CLR.

-   Компоненты могут содержать типы, реализующие логику приложения, элементы управления пользовательского интерфейса [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] или и те, и другие.

    > [!NOTE]
    >  Рекомендуется отделять элементы пользовательского интерфейса от логики приложения. Кроме того, нельзя использовать элементы управления пользовательского интерфейса [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] в приложении [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], созданном для Windows с помощью JavaScript и HTML.

-   Компонент может быть проектом внутри решения Visual Studio для приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] или многоразовым компонентом, который можно добавить к нескольким решениям.

    > [!NOTE]
    >  Если компонент будет использоваться только для C# или Visual Basic, нет причин делать его компонентом [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Если вы сделаете этот компонент обычной библиотекой классов .NET Framework, то вам не придется ограничивать открытый API-интерфейс только типами [!INCLUDE[wrt](../../../includes/wrt-md.md)].

-   Версии повторно используемых компонентов можно выпускать с использованием [!INCLUDE[wrt](../../../includes/wrt-md.md)] <xref:Windows.Foundation.Metadata.VersionAttribute> атрибут, чтобы определить, какие типы (и какие члены типа) добавлены в другой версии.

-   Типы в компоненте могут наследовать от типов [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Элементы управления могут наследовать от простых типов элементов управления в <xref:Windows.UI.Xaml.Controls.Primitives> пространства имен или от более оформленных элементов управления, такие как <xref:Windows.UI.Xaml.Controls.Button>.

    > [!IMPORTANT]
    >  Начиная с версий [!INCLUDE[win8](../../../includes/win8-md.md)] и [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], все открытые типы в управляемом компоненте [!INCLUDE[wrt](../../../includes/wrt-md.md)] необходимо запечатывать. Тип в другом компоненте [!INCLUDE[wrt](../../../includes/wrt-md.md)] не может быть производным от них. Если необходимо предоставить полиморфное расширения функциональности в компоненте, можно создать интерфейс и реализовать его в полиморфных типах.

-   Все типы параметров и возвращаемых значений открытых типов в компоненте должны быть типами [!INCLUDE[wrt](../../../includes/wrt-md.md)] (включая типы [!INCLUDE[wrt](../../../includes/wrt-md.md)], которые определяет компонент).

 Следующие разделы содержат примеры распространенных сценариев.

### <a name="application-logic-for-a-includewin8appnamelongincludeswin8-appname-long-mdmd-app-with-javascript"></a>Логика приложения для приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] с JavaScript
 При создании приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] для Windows с помощью JavaScript может оказаться, что некоторые части логики приложения работают лучше в управляемом коде или их легче так разработать. Javascript не может использовать библиотеки классов платформы .NET Framework непосредственно, но можно сделать библиотекой классов файл .WinMD. В этом сценарии компонент [!INCLUDE[wrt](../../../includes/wrt-md.md)] является неотъемлемой частью приложения, поэтому не имеет смысла указывать атрибуты версии.

### <a name="reusable-includewin8appnamelongincludeswin8-appname-long-mdmd-ui-controls"></a>Повторно используемые элементы управления пользовательского интерфейса [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]
 Можно упаковать набор связанных элементов управления пользовательского интерфейса в многократно используемый компонент [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Компонент может распространяться сам по себе или использоваться как элемент в приложениях, которые вы создаете. В этом случае имеет смысл использовать [!INCLUDE[wrt](../../../includes/wrt-md.md)] <xref:Windows.Foundation.Metadata.VersionAttribute> атрибут для улучшения совместимости.

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>Логика приложения с возможностью повторного использования существующих приложений платформы .NET Framework
 Можно упаковать управляемый код из существующих классических приложений в виде автономного компонента [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Это позволит использовать его в приложениях [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], созданных с помощью C++ или JavaScript, а также в приложениях [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], созданных с помощью C# или Visual Basic. Используйте управление версиями, если этот код будет использоваться в нескольких местах.

## <a name="related-topics"></a>См. также

|Заголовок|Описание|
|-----------|-----------------|
|[Общие сведения о платформе .NET для приложений Магазина Windows](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))|Описывает типы и члены платформы .NET Framework, которые можно использовать для создания приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] и компонентов [!INCLUDE[wrt](../../../includes/wrt-md.md)]. (В Центре разработки для Windows.)|
|[Схема создания приложений Windows Store, с помощью C# или Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10))|Предоставляет основные ресурсы, помогающие начать разрабатывать приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] с помощью C# или Visual Basic, а также многие разделы краткого руководства, правила и рекомендации. (В Центре разработки для Windows.)|
|[Как и инструкции (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))|Предоставляет основные ресурсы, помогающие начать разрабатывать приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] с помощью C# или Visual Basic, а также многие разделы краткого руководства, правила и рекомендации. (В Центре разработки для Windows.)|
|[Создание компонентов среды выполнения Windows в C# и Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|Описывает процесс создания компонента [!INCLUDE[wrt](../../../includes/wrt-md.md)] с помощью платформы .NET Framework, объясняет, как использовать его как часть приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], созданного для Windows с использованием JavaScript, а также описывает процесс отладки с помощью Visual Studio. (В Центре разработки для Windows.)|
|[Ссылка на среды выполнения Windows](/uwp/api/)|Справочная документация по [!INCLUDE[wrt](../../../includes/wrt-md.md)]. (В Центре разработки для Windows.)|
|[Передача URI в среду выполнения Windows](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)|Описывает проблемы, которые могут возникнуть при передаче адреса URI из управляемого кода в [!INCLUDE[wrt](../../../includes/wrt-md.md)], а также содержит сведения о способах их устранения.|
