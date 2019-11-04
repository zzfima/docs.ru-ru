---
title: Синтаксис PropertyPath XAML
ms.date: 03/30/2017
helpviewer_keywords:
- PropertyPath object [WPF]
- XAML [WPF], PropertyPath object
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
ms.openlocfilehash: b2530793bfe1a158a0df1c34b2768e0c7ca351f3
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459362"
---
# <a name="propertypath-xaml-syntax"></a>Синтаксис PropertyPath XAML

Объект <xref:System.Windows.PropertyPath> поддерживает сложный встроенный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] синтаксис для установки различных свойств, которые принимают тип <xref:System.Windows.PropertyPath> в качестве значения. В этом разделе документируется синтаксис <xref:System.Windows.PropertyPath>, примененный к синтаксису привязки и анимации.

<a name="where"></a>

## <a name="where-propertypath-is-used"></a>Где используется PropertyPath

<xref:System.Windows.PropertyPath> — это общий объект, используемый в нескольких [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]ных функциях. Несмотря на использование общих <xref:System.Windows.PropertyPath> для передачи сведений о пути к свойству, использование каждой функциональной области, где <xref:System.Windows.PropertyPath> используется в качестве типа, различается. Таким образом, более практично документировать синтаксис для каждой функции.

В основном [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует <xref:System.Windows.PropertyPath> для описания путей к объектной модели для обхода свойств источника данных объекта и для описания целевого пути для целевых анимаций.

Некоторые свойства стиля и шаблона, такие как <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType>, имеют полное имя свойства, которое внешне напоминает <xref:System.Windows.PropertyPath>. Но это не правда <xref:System.Windows.PropertyPath>; Вместо этого он является полным *владельцем.* использование формата строки свойства, включенного процессором [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] WPF в сочетании с преобразователем типов для <xref:System.Windows.DependencyProperty>.

<a name="databinding_s"></a>

## <a name="propertypath-for-objects-in-data-binding"></a>PropertyPath для объектов в привязке данных

Привязка данных является функцией [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которую можно привязать к целевому значению любого свойства зависимостей. Однако источник такой привязки данных не обязательно должен быть свойством зависимостей. Это может быть любой тип свойства, распознаваемый применимым поставщиком данных. Пути к свойствам особенно используются для <xref:System.Windows.Data.ObjectDataProvider>, который используется для получения источников привязки из объектов среды CLR и их свойств.

Обратите внимание, что привязка данных к [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] не использует <xref:System.Windows.PropertyPath>, так как не использует <xref:System.Windows.Data.Binding.Path%2A> в <xref:System.Windows.Data.Binding>. Вместо этого используйте <xref:System.Windows.Data.Binding.XPath%2A> и укажите допустимый синтаксис XPath в [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)] данных. <xref:System.Windows.Data.Binding.XPath%2A> также указывается в виде строки, но здесь не описывается. см. статью [Привязка к XML-данным с помощью XmlDataProvider и запросов XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).

Ключом к пониманию путей к свойствам в привязке к данным является то, что можно настроить целевой объект привязки на отдельное значение свойства либо использовать привязку к целевым свойствам, которые принимают списки или коллекции. При привязке коллекций для привязки к экземпляру <xref:System.Windows.Controls.ListBox>, который будет расширяться в зависимости от количества элементов данных в коллекции, путь к свойству должен ссылаться на объект коллекции, а не на отдельные элементы коллекции. Обработчик привязки данных будет сопоставлять коллекцию, используемую в качестве источника данных, с типом целевого объекта привязки автоматически, что приводит к поведению, например заполнению <xref:System.Windows.Controls.ListBox> массивом элементов.

<a name="singlecurrent"></a>

### <a name="single-property-on-the-immediate-object-as-data-context"></a>Одиночное свойство в объекте интерпретации в качестве контекста данных

```xml
<Binding Path="propertyName" .../>
```

*PropertyName* должен быть разрешен в качестве имени свойства, которое находится в текущем <xref:System.Windows.FrameworkElement.DataContext%2A> для использования <xref:System.Windows.Data.Binding.Path%2A>. Если привязка обновляет источник, это свойство должно быть доступно для чтения и записи, а исходный объект должен быть изменяемым.

<a name="singleindex"></a>

### <a name="single-indexer-on-the-immediate-object-as-data-context"></a>Одиночный индексатор в объекте интерпретации в контексте данных

```xml
<Binding Path="[key]" .../>
```

`key` должен быть либо типизированным индексом для словаря или хэш-таблицы, либо целочисленным индексом массива. Кроме того, значение ключа должно быть типом, который можно непосредственно привязать к свойству, в котором оно применяется. Например, хэш-таблица, содержащая строковые ключи и строковые значения, может использоваться таким образом для привязки к тексту для <xref:System.Windows.Controls.TextBox>. Либо, если ключ указывает на коллекцию или субиндекс, этот синтаксис можно использовать для привязки к целевому свойству коллекции. В противном случае необходимо ссылаться на конкретное свойство, например с помощью синтаксиса `<Binding Path="[key].propertyName" .../>`.

При необходимости можно указать тип индекса. Дополнительные сведения об этом аспекте пути индексированного свойства см. в разделе <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.

<a name="multipleindirect"></a>

### <a name="multiple-property-indirect-property-targeting"></a>Несколько свойств (косвенное назначение свойства)

```xml
<Binding Path="propertyName.propertyName2" .../>
```

`propertyName` должен быть разрешен в качестве имени свойства, которое является текущим <xref:System.Windows.FrameworkElement.DataContext%2A>ом. Свойствами пути `propertyName` и `propertyName2` могут быть любые свойства, которые существуют в связи, где `propertyName2` — свойство, которое существует в типе, являющемся значением `propertyName`.

<a name="singleattached"></a>

### <a name="single-property-attached-or-otherwise-type-qualified"></a>Одиночное свойство, присоединенное свойство или свойство с указанием типа

```xml
<object property="(ownerType.propertyName)" .../>
```

Круглые скобки указывают, что это свойство в <xref:System.Windows.PropertyPath> должно быть создано с использованием частичной квалификации. Может использоваться пространство имен XML для поиска типа с соответствующим сопоставлением. `ownerType` ищет типы, к которым обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] имеет доступ, через объявления <xref:System.Windows.Markup.XmlnsDefinitionAttribute> в каждой сборке. В большинстве приложений есть пространство имен XML по умолчанию, сопоставленное пространству имен [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)], поэтому префикс обычно требуется только для настраиваемых типов или типов вне этого пространства имен.  `propertyName` должно разрешаться как имя свойства, существующего в `ownerType`. Этот синтаксис обычно используется в одном из следующих случаев.

- Путь, указанный в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], который находится в стиле или шаблоне, не имеющем указанного целевого типа. Использование полных имен обычно недействительно для иных случаев, поскольку в отличие от стилей и шаблонов свойство существует в экземпляре, а не в типе.

- Свойство является присоединенным свойством.

- Выполняется привязка к статическому свойству.

Для использования в качестве цели раскадровки свойство, указанное как `propertyName`, должно быть <xref:System.Windows.DependencyProperty>.

<a name="sourcetraversal"></a>

### <a name="source-traversal-binding-to-hierarchies-of-collections"></a>Обход источников (привязка к иерархиям коллекций)

```xml
<object Path="propertyName/propertyNameX" .../>
```

/ в этом синтаксисе используется для навигации в иерархическом объекте источника данных. Поддерживается несколько шагов в иерархии с последовательными символами /. Обход источников учитывает текущую позицию указателя записи, которая определяется синхронизацией данных с пользовательским интерфейсом его представления. Дополнительные сведения о привязке к иерархическим объектам источника данных и концепции указателя текущей записи в привязке данных см. в разделе [Использование шаблона "Основной/подробности" с иерархическими данными](../data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) или [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md).

> [!NOTE]
> Внешне этот синтаксис походит на [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)]. Истинное [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] выражение для привязки к [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] источнику данных не используется как значение <xref:System.Windows.Data.Binding.Path%2A> и должно использоваться для взаимоисключающего свойства <xref:System.Windows.Data.Binding.XPath%2A>.

### <a name="collection-views"></a>Представления коллекций

Для ссылки на представление именованной коллекции перед именем представления используется символ решетки (`#`).

### <a name="current-record-pointer"></a>Указатель текущей записи

Чтобы ссылаться на указатель текущей записи для представления коллекции или сценария привязки данных "Основной/подробности", в начале строки пути поставьте косую черту (`/`). Обход любого пути, проходящего через косую черту, начинается с указателя текущей записи.

### <a name="multiple-indexers"></a>Несколько индексаторов

```xaml
<object Path="[index1,index2...]" .../>
```

или

```xaml
<object Path="propertyName[index,index2...]" .../>
```

Если данный объект поддерживает несколько индексаторов, их можно указать по порядку, аналогично синтаксису ссылок на массив. Рассматриваемый объект может быть либо текущим контекстом, либо значением свойства, содержащего объект с несколькими индексами.

По умолчанию значения индексатора вводятся с использованием характеристик базового объекта. При необходимости можно указать тип индекса. Дополнительные сведения о вводе индексаторов см. в разделе <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.

<a name="mixing"></a>

### <a name="mixing-syntaxes"></a>Смешанные синтаксисы

Можно смешивать все синтаксисы, показанные выше. Например, ниже приведен пример, в котором создается путь к свойству для цвета в определенном x, y свойства `ColorGrid`, содержащем массивную сетку <xref:System.Windows.Media.SolidColorBrush> объектов:

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

Свойство Target анимации должно быть свойством зависимости, которое принимает либо <xref:System.Windows.Freezable>, либо примитивный тип. Однако целевое свойство типа и конечное анимированное свойство могут существовать в различных объектах. Для анимаций путь к свойству используется для определения связи между свойством целевого объекта именованной анимации и заданным целевым свойством анимации путем обхода отношений "объект/свойство" в значениях свойств.

<a name="general"></a>

### <a name="general-object-property-considerations-for-animations"></a>Общие рекомендации для отношений "объект/свойство" для анимаций

Подробнее о концепциях анимации в целом см. в разделах [Общие сведения о раскадровке ](../graphics-multimedia/storyboards-overview.md) и [Общие сведения об анимации ](../graphics-multimedia/animation-overview.md).

Тип значения или анимированное свойство должны быть либо типом <xref:System.Windows.Freezable>, либо примитивом. Свойство, запускающее путь, должно быть разрешено в качестве имени свойства зависимости, существующего для указанного типа <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>.

Для поддержки клонирования для анимации <xref:System.Windows.Freezable>, которая уже заморожена, объект, заданный <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>, должен быть <xref:System.Windows.FrameworkElement>ным или <xref:System.Windows.FrameworkContentElement> производным классом.

<a name="singlestepanim"></a>

### <a name="single-property-on-the-target-object"></a>Одно свойство в целевом объекте

```xml
<animation Storyboard.TargetProperty="propertyName" .../>
```

`propertyName` должен быть разрешен в качестве имени свойства зависимостей, существующего в указанном типе <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>.

<a name="indirectanim"></a>

### <a name="indirect-property-targeting"></a>Косвенное назначение свойства

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>
```

`propertyName` должно быть свойством, которое является типом значения <xref:System.Windows.Freezable> или примитивом, который существует для указанного типа <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>.

`propertyName2` должно быть именем свойства зависимостей, существующего в объекте, который является значением `propertyName`. Иными словами, `propertyName2` должны существовать как свойство зависимостей для типа, который является `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>.

Косвенное назначение анимации необходимо из-за примененных стилей и шаблонов. Чтобы ориентироваться на анимацию, требуется <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> на целевом объекте, и это имя устанавливается с помощью [x:Name](../../xaml-services/x-name-directive.md) или <xref:System.Windows.FrameworkElement.Name%2A>. Хотя элементы шаблона и стиля также могут иметь имена, эти имена действительны только в области имен стиля и шаблона. (Если бы шаблоны и стили совместно использовали пространства имен с разметкой приложения, имена не могли бы быть уникальными. Стили и шаблоны буквально совместно используются экземплярами и будут постоянно дублировать имена.) Таким способом, если отдельные свойства элемента, которые вы хотели бы анимировать, поступили из стиля или шаблона, необходимо начать с именованного экземпляра элемента, который не относится к шаблону стиля, а затем перейти к визуальному дереву стиля или шаблона, чтобы оно поступало на свойство Вы хотите анимировать.

Например, свойство <xref:System.Windows.Controls.Panel.Background%2A> <xref:System.Windows.Controls.Panel> является полным <xref:System.Windows.Media.Brush> (фактически <xref:System.Windows.Media.SolidColorBrush>), полученным из шаблона темы. Чтобы полностью анимировать <xref:System.Windows.Media.Brush>, необходимо быть Брушаниматион (возможно, по одному для каждого типа <xref:System.Windows.Media.Brush>) и такого типа нет. Чтобы анимировать кисть, необходимо анимировать свойства определенного типа <xref:System.Windows.Media.Brush>. Чтобы применить <xref:System.Windows.Media.Animation.ColorAnimation>, необходимо получить от <xref:System.Windows.Media.SolidColorBrush> до <xref:System.Windows.Media.SolidColorBrush.Color%2A>. Путь к свойству в этом примере будет `Background.Color`.

<a name="attachedanim"></a>

### <a name="attached-properties"></a>Вложенные свойства

```xml
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>
```

Круглые скобки указывают, что это свойство в <xref:System.Windows.PropertyPath> должно быть создано с использованием частичной квалификации. Для поиска типа может использоваться пространство имен XML. `ownerType` ищет типы, к которым обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] имеет доступ, через объявления <xref:System.Windows.Markup.XmlnsDefinitionAttribute> в каждой сборке. В большинстве приложений есть пространство имен XML по умолчанию, сопоставленное пространству имен [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)], поэтому префикс обычно требуется только для настраиваемых типов или типов вне этого пространства имен. `propertyName` должно разрешаться как имя свойства, существующего в `ownerType`. Свойство, указанное как `propertyName`, должно быть <xref:System.Windows.DependencyProperty>. (Все присоединенные свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализуются как свойства взаимозависимостей, поэтому эта проблема возникает только для настраиваемых присоединенных свойств.)

<a name="indexanim"></a>

### <a name="indexers"></a>Индексаторы

```xml
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>
```

Большинство свойств зависимости или типов <xref:System.Windows.Freezable> не поддерживают индексатор. Таким образом, единственное использование индексатора в пути к анимации — это промежуточное положение между свойством, которое запускает цепочку в именованном целевом объекте и конечным анимированным свойством. В предоставленном синтаксисе это `propertyName2`. Например, может потребоваться использование индексатора, если промежуточное свойство является коллекцией, например <xref:System.Windows.Media.TransformGroup>, в пути к свойству, например `RenderTransform.Children[1].Angle`.

<a name="ppincode"></a>

## <a name="propertypath-in-code"></a>PropertyPath в коде

Использование кода для <xref:System.Windows.PropertyPath>, включая создание <xref:System.Windows.PropertyPath>, описано в справочном разделе, посвященном <xref:System.Windows.PropertyPath>.

В целом <xref:System.Windows.PropertyPath> предназначен для использования двух различных конструкторов: один для использования привязки и простейший способ использования анимации, а второй — для сложных использований анимации. Используйте <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> подпись для использования привязки, где объект является строкой. Используйте сигнатуру <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> для одношаговых путей анимации, где объект является <xref:System.Windows.DependencyProperty>. Используйте подпись <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> для сложных анимаций. Последний конструктор использует строку токена для первого параметра и массив объектов, которые заполняют позиции в строке токена, чтобы определить отношение пути к свойству.

## <a name="see-also"></a>См. также

- <xref:System.Windows.PropertyPath>
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Общие сведения о раскадровке](../graphics-multimedia/storyboards-overview.md)
