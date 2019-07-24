---
title: Синтаксис PropertyPath XAML
ms.date: 03/30/2017
helpviewer_keywords:
- PropertyPath object [WPF]
- XAML [WPF], PropertyPath object
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
ms.openlocfilehash: deebdb690a6ba831730701de2608089af2d6bdfd
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401661"
---
# <a name="propertypath-xaml-syntax"></a>Синтаксис PropertyPath XAML

Объект поддерживает сложный встроенный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] синтаксис для установки <xref:System.Windows.PropertyPath> различных свойств, которые принимают тип в качестве значения. <xref:System.Windows.PropertyPath> В <xref:System.Windows.PropertyPath> этом разделе документируется синтаксис, примененный к синтаксису привязки и анимации.

<a name="where"></a>

## <a name="where-propertypath-is-used"></a>Где используется PropertyPath

<xref:System.Windows.PropertyPath>— Это общий объект, используемый в нескольких [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] функциях. Несмотря на использование общих <xref:System.Windows.PropertyPath> для передачи сведений о пути к свойству, использование каждой области функций, где <xref:System.Windows.PropertyPath> используется в качестве типа, различается. Таким образом, более практично документировать синтаксис для каждой функции.

В основном <xref:System.Windows.PropertyPath> использует для описания путей объектной модели для обхода свойств источника данных объекта и для описания целевого пути для целевых анимаций. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]

Некоторые свойства стиля и шаблона, например <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType> , получают полное имя свойства, которое внешне напоминает. <xref:System.Windows.PropertyPath> Но это не значение <xref:System.Windows.PropertyPath>true, а является полным *владельцем.* использование формата строки свойства, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] включенное в сочетании с преобразователем типов для. <xref:System.Windows.DependencyProperty>

<a name="databinding_s"></a>

## <a name="propertypath-for-objects-in-data-binding"></a>PropertyPath для объектов в привязке данных

Привязка данных является функцией [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которую можно привязать к целевому значению любого свойства зависимостей. Однако источник такой привязки данных не обязательно должен быть свойством зависимостей. Это может быть любой тип свойства, распознаваемый применимым поставщиком данных. Пути к свойствам особенно используются для <xref:System.Windows.Data.ObjectDataProvider>, который используется для получения источников привязки из объектов среды CLR и их свойств.

Обратите внимание, что [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] привязка данных не <xref:System.Windows.PropertyPath>использует, так как она не <xref:System.Windows.Data.Binding.Path%2A> используется в <xref:System.Windows.Data.Binding>. Вместо этого используется <xref:System.Windows.Data.Binding.XPath%2A> и указывается допустимый синтаксис XPath [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)] в данных. <xref:System.Windows.Data.Binding.XPath%2A>также указывается в виде строки, но здесь не описывается. см. статью [Привязка к XML-данным с помощью XmlDataProvider и запросов XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).

Ключом к пониманию путей к свойствам в привязке к данным является то, что можно настроить целевой объект привязки на отдельное значение свойства либо использовать привязку к целевым свойствам, которые принимают списки или коллекции. При привязке коллекций для привязки <xref:System.Windows.Controls.ListBox> экземпляра, который будет расширяться в зависимости от количества элементов данных в коллекции, путь к свойству должен ссылаться на объект коллекции, а не на отдельные элементы коллекции. Обработчик привязки данных будет сопоставлять коллекцию, используемую в качестве источника данных, с типом целевого объекта привязки автоматически, что приводит к <xref:System.Windows.Controls.ListBox> поведению, например заполнению с массивом элементов.

<a name="singlecurrent"></a>

### <a name="single-property-on-the-immediate-object-as-data-context"></a>Одиночное свойство в объекте интерпретации в качестве контекста данных

```xml
<Binding Path="propertyName" .../>
```

*PropertyName* должен быть разрешен в качестве имени свойства, которое находится в текущем <xref:System.Windows.FrameworkElement.DataContext%2A> экземпляре для <xref:System.Windows.Data.Binding.Path%2A> использования. Если привязка обновляет источник, это свойство должно быть доступно для чтения и записи, а исходный объект должен быть изменяемым.

<a name="singleindex"></a>

### <a name="single-indexer-on-the-immediate-object-as-data-context"></a>Одиночный индексатор в объекте интерпретации в контексте данных

```xml
<Binding Path="[key]" .../>
```

`key` должен быть либо типизированным индексом для словаря или хэш-таблицы, либо целочисленным индексом массива. Кроме того, значение ключа должно быть типом, который можно непосредственно привязать к свойству, в котором оно применяется. Например, хэш-таблица, содержащая строковые ключи и строковые значения, может использоваться таким образом для привязки к тексту <xref:System.Windows.Controls.TextBox>для. Либо, если ключ указывает на коллекцию или субиндекс, этот синтаксис можно использовать для привязки к целевому свойству коллекции. В противном случае необходимо ссылаться на конкретное свойство, например с помощью синтаксиса `<Binding Path="[key].propertyName" .../>`.

При необходимости можно указать тип индекса. Дополнительные сведения об этом аспекте пути индексированного свойства см. в <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>разделе.

<a name="multipleindirect"></a>

### <a name="multiple-property-indirect-property-targeting"></a>Несколько свойств (косвенное назначение свойства)

```xml
<Binding Path="propertyName.propertyName2" .../>
```

`propertyName`должен быть разрешен в качестве имени свойства, которое является текущим <xref:System.Windows.FrameworkElement.DataContext%2A>. Свойствами пути `propertyName` и `propertyName2` могут быть любые свойства, которые существуют в связи, где `propertyName2` — свойство, которое существует в типе, являющемся значением `propertyName`.

<a name="singleattached"></a>

### <a name="single-property-attached-or-otherwise-type-qualified"></a>Одиночное свойство, присоединенное свойство или свойство с указанием типа

```xml
<object property="(ownerType.propertyName)" .../>
```

Круглые скобки указывают, что это свойство в <xref:System.Windows.PropertyPath> должно быть создано с использованием частичной квалификации. Может использоваться пространство имен XML для поиска типа с соответствующим сопоставлением. Поисковые типы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ,<xref:System.Windows.Markup.XmlnsDefinitionAttribute> к которым обработчик имеет доступ, через объявления в каждой сборке. `ownerType` В большинстве приложений есть пространство имен XML по умолчанию, сопоставленное пространству имен [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)], поэтому префикс обычно требуется только для настраиваемых типов или типов вне этого пространства имен.  `propertyName` должно разрешаться как имя свойства, существующего в `ownerType`. Этот синтаксис обычно используется в одном из следующих случаев.

- Путь, указанный в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], который находится в стиле или шаблоне, не имеющем указанного целевого типа. Использование полных имен обычно недействительно для иных случаев, поскольку в отличие от стилей и шаблонов свойство существует в экземпляре, а не в типе.

- Свойство является присоединенным свойством.

- Выполняется привязка к статическому свойству.

Для использования в качестве цели раскадровки свойство, `propertyName` указанное как, <xref:System.Windows.DependencyProperty>должно иметь значение.

<a name="sourcetraversal"></a>

### <a name="source-traversal-binding-to-hierarchies-of-collections"></a>Обход источников (привязка к иерархиям коллекций)

```xml
<object Path="propertyName/propertyNameX" .../>
```

/ в этом синтаксисе используется для навигации в иерархическом объекте источника данных. Поддерживается несколько шагов в иерархии с последовательными символами /. Обход источников учитывает текущую позицию указателя записи, которая определяется синхронизацией данных с пользовательским интерфейсом его представления. Дополнительные сведения о привязке к иерархическим объектам источника данных и концепции указателя текущей записи в привязке данных см. в разделе [Использование шаблона "Основной/подробности" с иерархическими данными](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) или [Общие сведения о привязке данных](../data/data-binding-overview.md).

> [!NOTE]
> Внешне этот синтаксис походит на [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)]. Истинное [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] выражение для привязки [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] к источнику данных не используется в качестве <xref:System.Windows.Data.Binding.Path%2A> значения и вместо этого должно использоваться для взаимоисключающего <xref:System.Windows.Data.Binding.XPath%2A> свойства.

### <a name="collection-views"></a>Представления коллекций

Для ссылки на представление именованной коллекции перед именем представления используется символ решетки (`#`).

### <a name="current-record-pointer"></a>Указатель текущей записи

Чтобы ссылаться на указатель текущей записи для представления коллекции или сценария привязки данных "Основной/подробности", в начале строки пути поставьте косую черту (`/`). Обход любого пути, проходящего через косую черту, начинается с указателя текущей записи.

### <a name="multiple-indexers"></a>Несколько индексаторов

```xaml
<object Path="[index1,index2...]" .../>
```

или диспетчер конфигурации служб

```xaml
<object Path="propertyName[index,index2...]" .../>
```

Если данный объект поддерживает несколько индексаторов, их можно указать по порядку, аналогично синтаксису ссылок на массив. Рассматриваемый объект может быть либо текущим контекстом, либо значением свойства, содержащего объект с несколькими индексами.

По умолчанию значения индексатора вводятся с использованием характеристик базового объекта. При необходимости можно указать тип индекса. Дополнительные сведения о вводе индексаторов см. <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>в разделе.

<a name="mixing"></a>

### <a name="mixing-syntaxes"></a>Смешанные синтаксисы

Можно смешивать все синтаксисы, показанные выше. Например, ниже приведен пример, который создает путь к свойству для цвета в определенном x, y `ColorGrid` свойства, которое содержит <xref:System.Windows.Media.SolidColorBrush> массив объектов в виде пиксельной сетки.

```xml
<Rectangle Fill="{Binding ColorGrid[20,30].SolidColorBrushResult}" .../>
```

### <a name="escapes-for-property-path-strings"></a>Escape-символы для строк путей к свойствам

Для некоторых бизнес-объектов может возникнуть случай, когда для правильного анализа строки пути к свойству требуется escape-последовательность. Такая необходимость должна возникать редко, так как многие из этих символов имеют аналогичные проблемы взаимодействия при именовании в языках, которые обычно используются для определения бизнес-объекта.

- Внутри индексаторов ([ ]) символ каретки (^) служит escape-символом для следующего символа.

- Необходимо предварять escape-символами (используя XML-сущности) определенные символы, которые являются специальными для определения языка XML. Используйте `&` в качестве escape-символа для символа &. Используйте `>` в качестве escape-символа для символа >.

- Необходимо предварять escape-символами (с помощью обратной косой черты `\`) символы, которые являются специальными для поведения средства синтаксического анализа WPF XAML для обработки расширения разметки.

  - Обратная косая черта (`\`) сама по себе является escape-символом.

  - Знак равенства (`=`) разделяет имя и значение свойства.

  - Запятая (`,`) разделяет свойства.

  - Закрывающая фигурная скобка (`}`) — это конец расширения разметки.

> [!NOTE]
> С технической точки зрения, эти escape-последовательности также работают для пути к свойству раскадровки, но обычно объектные модели обходятся для существующих объектов WPF и использование escape-символов не требуется.

<a name="databinding_sa"></a>

## <a name="propertypath-for-animation-targets"></a>PropertyPath для целевых объектов анимации

Целевое свойство анимации должно быть свойством зависимости, которое принимает <xref:System.Windows.Freezable> или либо примитивный тип. Однако целевое свойство типа и конечное анимированное свойство могут существовать в различных объектах. Для анимаций путь к свойству используется для определения связи между свойством целевого объекта именованной анимации и заданным целевым свойством анимации путем обхода отношений "объект/свойство" в значениях свойств.

<a name="general"></a>

### <a name="general-object-property-considerations-for-animations"></a>Общие рекомендации для отношений "объект/свойство" для анимаций

Подробнее о концепциях анимации в целом см. в разделах [Общие сведения о раскадровке ](../graphics-multimedia/storyboards-overview.md) и [Общие сведения об анимации ](../graphics-multimedia/animation-overview.md).

Тип значения или анимированное свойство должны быть либо <xref:System.Windows.Freezable> типом, либо примитивом. Свойство, запускающее путь, должно быть разрешено в качестве имени свойства зависимостей, существующего для указанного <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> типа.

<xref:System.Windows.Freezable> Для поддержки клонирования для анимации, которая уже заморожена, объект, указанный параметром <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> , должен быть <xref:System.Windows.FrameworkElement> производным классом или <xref:System.Windows.FrameworkContentElement> .

<a name="singlestepanim"></a>

### <a name="single-property-on-the-target-object"></a>Одно свойство в целевом объекте

```xml
<animation Storyboard.TargetProperty="propertyName" .../>
```

`propertyName`необходимо разрешить в виде имени свойства зависимостей, существующего в указанном <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> типе.

<a name="indirectanim"></a>

### <a name="indirect-property-targeting"></a>Косвенное назначение свойства

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>
```

`propertyName`должно быть свойством, которое является либо <xref:System.Windows.Freezable> типом значения, либо примитивом, который существует для указанного <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> типа.

`propertyName2` должно быть именем свойства зависимостей, существующего в объекте, который является значением `propertyName`. Иными словами, `propertyName2` должен существовать как свойство зависимостей для типа, который `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>является.

Косвенное назначение анимации необходимо из-за примененных стилей и шаблонов. Чтобы ориентироваться на анимацию, <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> требуется объект на целевом объекте, и это имя устанавливается с помощью [x:Name](../../xaml-services/x-name-directive.md) или. <xref:System.Windows.FrameworkElement.Name%2A> Хотя элементы шаблона и стиля также могут иметь имена, эти имена действительны только в области имен стиля и шаблона. (Если бы шаблоны и стили совместно использовали пространства имен с разметкой приложения, имена не могли бы быть уникальными. Стили и шаблоны буквально разделяются между экземплярами и могут сохранять повторяющиеся имена). Таким образом, если отдельные свойства элемента, которые нужно анимировать, исходят из стиля или шаблона, то нужно начать с именованного экземпляра элемента, который не происходит из шаблона стиля. Затем укажите целевой объект в визуальном дереве стиля или шаблона, чтобы достичь свойства, которое нужно анимировать.

Например, <xref:System.Windows.Controls.Panel.Background%2A> свойство <xref:System.Windows.Controls.Panel> объекта является полным <xref:System.Windows.Media.Brush> (фактически <xref:System.Windows.Media.SolidColorBrush>), полученным из шаблона темы. Чтобы <xref:System.Windows.Media.Brush> полностью анимировать анимацию, необходимо быть брушаниматион (возможно, по одному для каждого <xref:System.Windows.Media.Brush> типа) и такого типа нет. Чтобы анимировать кисть, необходимо анимировать свойства определенного <xref:System.Windows.Media.Brush> типа. Чтобы применить <xref:System.Windows.Media.SolidColorBrush> его<xref:System.Windows.Media.Animation.ColorAnimation> , необходимо получить из. <xref:System.Windows.Media.SolidColorBrush.Color%2A> Путь к свойству в этом примере будет `Background.Color`.

<a name="attachedanim"></a>

### <a name="attached-properties"></a>Вложенные свойства

```xml
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>
```

Круглые скобки указывают, что это свойство в <xref:System.Windows.PropertyPath> должно быть создано с использованием частичной квалификации. Для поиска типа может использоваться пространство имен XML. Поисковые типы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ,<xref:System.Windows.Markup.XmlnsDefinitionAttribute> к которым обработчик имеет доступ, через объявления в каждой сборке. `ownerType` В большинстве приложений есть пространство имен XML по умолчанию, сопоставленное пространству имен [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)], поэтому префикс обычно требуется только для настраиваемых типов или типов вне этого пространства имен. `propertyName` должно разрешаться как имя свойства, существующего в `ownerType`. Свойство, указанное как `propertyName` , должно иметь <xref:System.Windows.DependencyProperty>значение. (Все присоединенные свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализуются как свойства взаимозависимостей, поэтому эта проблема возникает только для настраиваемых присоединенных свойств.)

<a name="indexanim"></a>

### <a name="indexers"></a>Индексаторы

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>
```

Большинство свойств или <xref:System.Windows.Freezable> типов зависимостей не поддерживает индексатор. Таким образом, единственное использование индексатора в пути к анимации — это промежуточное положение между свойством, которое запускает цепочку в именованном целевом объекте и конечным анимированным свойством. В предоставленном синтаксисе это `propertyName2`. Например, может потребоваться использование индексатора, если промежуточное свойство является коллекцией <xref:System.Windows.Media.TransformGroup>, например, в пути к свойству, `RenderTransform.Children[1].Angle`например.

<a name="ppincode"></a>

## <a name="propertypath-in-code"></a>PropertyPath в коде

Использование кода для <xref:System.Windows.PropertyPath>, включая <xref:System.Windows.PropertyPath>создание, описано в разделе справки по <xref:System.Windows.PropertyPath>.

В целом, <xref:System.Windows.PropertyPath> предназначен для использования двух различных конструкторов: один для использования привязки и простейший способ использования анимации и один для сложных использований анимации. <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> Используйте сигнатуру для использования привязки, где объект является строкой. Используйте сигнатуру для одношаговых путей анимации, где объект <xref:System.Windows.DependencyProperty>является. <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> Используйте сигнатуру для сложных анимаций. Последний конструктор использует строку токена для первого параметра и массив объектов, которые заполняют позиции в строке токена, чтобы определить отношение пути к свойству.

## <a name="see-also"></a>См. также

- <xref:System.Windows.PropertyPath>
- [Общие сведения о привязке данных](../data/data-binding-overview.md)
- [Общие сведения о раскадровке](../graphics-multimedia/storyboards-overview.md)
