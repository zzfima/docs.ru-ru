---
title: Синтаксис PropertyPath XAML
ms.date: 03/30/2017
helpviewer_keywords:
- PropertyPath object [WPF]
- XAML [WPF], PropertyPath object
ms.assetid: 0e3cdf07-abe6-460a-a9af-3764b4fd707f
ms.openlocfilehash: 547c7d009d2fecf863284324c7ea45006d20d20c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548991"
---
# <a name="propertypath-xaml-syntax"></a>Синтаксис PropertyPath XAML
<xref:System.Windows.PropertyPath> Поддерживает сложные встроенный объект [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] синтаксис для настройки различных свойств, которые принимают <xref:System.Windows.PropertyPath> тип со своим значением. Этот раздел документы <xref:System.Windows.PropertyPath> синтаксис применительно к синтаксисы привязки и анимации.  
    
  
<a name="where"></a>   
## <a name="where-propertypath-is-used"></a>Где используется PropertyPath  
 <xref:System.Windows.PropertyPath> представляет собой общий объект, который используется в нескольких [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] функции. Несмотря на использование общего <xref:System.Windows.PropertyPath> для передачи сведений о пути свойства, параметры использования для каждой области функций где <xref:System.Windows.PropertyPath> используется как тип варьироваться. Таким образом, более практично документировать синтаксис для каждой функции.  
  
 В первую очередь [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует <xref:System.Windows.PropertyPath> для описания пути объектной модели для нахождения свойств объекта источника данных и для описания целевой путь для целевой анимации.  
  
 Некоторые свойства стилей и шаблонов, таких как <xref:System.Windows.Setter.Property%2A?displayProperty=nameWithType> занять свойство полное имя, которое внешне напоминает <xref:System.Windows.PropertyPath>. Но это не подлинный <xref:System.Windows.PropertyPath>; вместо этого используется полное *owner.property* строковое формат использования, включенный по WPF [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора в сочетании с преобразователь типов для <xref:System.Windows.DependencyProperty>.  
  
<a name="databinding_s"></a>   
## <a name="propertypath-for-objects-in-data-binding"></a>PropertyPath для объектов в привязке данных  
 Привязка данных является функцией [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которую можно привязать к целевому значению любого свойства зависимостей. Однако источник такой привязки данных не обязательно должен быть свойством зависимостей. Это может быть любой тип свойства, распознаваемый применимым поставщиком данных. Пути свойств используются особенно для <xref:System.Windows.Data.ObjectDataProvider>, который используется для получения источников привязки из [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] объекты и их свойства.  
  
 Обратите внимание, привязку данных к [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] не использует <xref:System.Windows.PropertyPath>, так как он не использует <xref:System.Windows.Data.Binding.Path%2A> в <xref:System.Windows.Data.Binding>. Вместо этого использовать <xref:System.Windows.Data.Binding.XPath%2A> и укажите допустимый синтаксис XPath в [!INCLUDE[TLA#tla_xmldom](../../../../includes/tlasharptla-xmldom-md.md)] данных. <xref:System.Windows.Data.Binding.XPath%2A> также указывается в виде строки, но не описано здесь; в разделе [связывания XML-данных с помощью XMLDataProvider и запросы XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Ключом к пониманию путей к свойствам в привязке к данным является то, что можно настроить целевой объект привязки на отдельное значение свойства либо использовать привязку к целевым свойствам, которые принимают списки или коллекции. При связывании коллекций, например привязки <xref:System.Windows.Controls.ListBox> , будет расширяться в зависимости от количества элементов данных в коллекции, а затем путь свойства должен ссылаться на объект коллекции, не на отдельные элементы коллекции. Механизм привязки данных будет соответствовать коллекции, используемой как источник данных для типа целевого объекта привязки автоматически, что приводит к заполнению <xref:System.Windows.Controls.ListBox> массивом элементов.  
  
<a name="singlecurrent"></a>   
### <a name="single-property-on-the-immediate-object-as-data-context"></a>Одиночное свойство в объекте интерпретации в качестве контекста данных  
  
```xml  
<Binding Path="propertyName" .../>  
```  
  
 *propertyName* необходимо разрешить имя свойства, которое относится к текущему <xref:System.Windows.FrameworkElement.DataContext%2A> для <xref:System.Windows.Data.Binding.Path%2A> использования. Если привязка обновляет источник, это свойство должно быть доступно для чтения и записи, а исходный объект должен быть изменяемым.  
  
<a name="singleindex"></a>   
### <a name="single-indexer-on-the-immediate-object-as-data-context"></a>Одиночный индексатор в объекте интерпретации в контексте данных  
  
```xml  
<Binding Path="[key]" .../>  
```  
  
 `key` должен быть либо типизированным индексом для словаря или хэш-таблицы, либо целочисленным индексом массива. Кроме того, значение ключа должно быть типом, который можно непосредственно привязать к свойству, в котором оно применяется. Например, хэш-таблицу, содержащую строковых ключей и строковых значений можно использовать таким образом для привязки к тексту для <xref:System.Windows.Controls.TextBox>. Либо, если ключ указывает на коллекцию или субиндекс, этот синтаксис можно использовать для привязки к целевому свойству коллекции. В противном случае необходимо ссылаться на конкретное свойство, например с помощью синтаксиса `<Binding Path="[``key``].``propertyName``" .../>`.  
  
 При необходимости можно указать тип индекса. Дополнительные сведения об этом аспекте индексированного пути свойства см. в разделе <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.  
  
<a name="multipleindirect"></a>   
### <a name="multiple-property-indirect-property-targeting"></a>Несколько свойств (косвенное назначение свойства)  
  
```xml  
<Binding Path="propertyName.propertyName2" .../>  
```  
  
 `propertyName` необходимо разрешить имя свойства, которое является текущим <xref:System.Windows.FrameworkElement.DataContext%2A>. Свойствами пути `propertyName` и `propertyName2` могут быть любые свойства, которые существуют в связи, где `propertyName2` — свойство, которое существует в типе, являющемся значением `propertyName`.  
  
<a name="singleattached"></a>   
### <a name="single-property-attached-or-otherwise-type-qualified"></a>Одиночное свойство, присоединенное свойство или свойство с указанием типа  
  
```xml  
<object property="(ownerType.propertyName)" .../>  
```  
  
 Скобки указывают, что это свойство в <xref:System.Windows.PropertyPath> должен быть создан с помощью частичного уточнения. Может использоваться пространство имен XML для поиска типа с соответствующим сопоставлением. `ownerType` Поиск типов, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор имеет доступ, с помощью <xref:System.Windows.Markup.XmlnsDefinitionAttribute> объявления в каждой сборке. В большинстве приложений есть пространство имен XML по умолчанию, сопоставленное пространству имен [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)], поэтому префикс обычно требуется только для настраиваемых типов или типов вне этого пространства имен.  `propertyName` должно разрешаться как имя свойства, существующего в `ownerType`. Этот синтаксис обычно используется в одном из следующих случаев.  
  
-   Путь, указанный в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], который находится в стиле или шаблоне, не имеющем указанного целевого типа. Использование полных имен обычно недействительно для иных случаев, поскольку в отличие от стилей и шаблонов свойство существует в экземпляре, а не в типе.  
  
-   Свойство является присоединенным свойством.  
  
-   Выполняется привязка к статическому свойству.  
  
 Для использования в качестве цели раскадровки, свойство указано как `propertyName` должен быть <xref:System.Windows.DependencyProperty>.  
  
<a name="sourcetraversal"></a>   
### <a name="source-traversal-binding-to-hierarchies-of-collections"></a>Обход источников (привязка к иерархиям коллекций)  
  
```xml  
<object Path="propertyName/propertyNameX" .../>  
```  
  
 / в этом синтаксисе используется для навигации в иерархическом объекте источника данных. Поддерживается несколько шагов в иерархии с последовательными символами /. Обход источников учитывает текущую позицию указателя записи, которая определяется синхронизацией данных с пользовательским интерфейсом его представления. Дополнительные сведения о привязке к иерархическим объектам источника данных и концепции указателя текущей записи в привязке данных см. в разделе [Использование шаблона "Основной/подробности" с иерархическими данными](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) или [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
> [!NOTE]
>  Внешне этот синтаксис походит на [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)]. Значение true [!INCLUDE[TLA2#tla_xpath](../../../../includes/tla2sharptla-xpath-md.md)] выражение для привязки к [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] источник данных не используется в качестве <xref:System.Windows.Data.Binding.Path%2A> значение и вместо этого следует использовать для взаимно исключают <xref:System.Windows.Data.Binding.XPath%2A> свойство.  
  
### <a name="collection-views"></a>Представления коллекций  
 Для ссылки на представление именованной коллекции перед именем представления используется символ решетки (`#`).  
  
### <a name="current-record-pointer"></a>Указатель текущей записи  
 Чтобы ссылаться на указатель текущей записи для представления коллекции или сценария привязки данных "Основной/подробности", в начале строки пути поставьте косую черту (`/`). Обход любого пути, проходящего через косую черту, начинается с указателя текущей записи.  
  
### <a name="multiple-indexers"></a>Несколько индексаторов  
  
```  
<object Path="[index1,index2...]" .../>  
or  
<object Path="propertyName[index,index2...]" .../>  
```  
  
 Если данный объект поддерживает несколько индексаторов, их можно указать по порядку, аналогично синтаксису ссылок на массив. Рассматриваемый объект может быть либо текущим контекстом, либо значением свойства, содержащего объект с несколькими индексами.  
  
 По умолчанию значения индексатора вводятся с использованием характеристик базового объекта. При необходимости можно указать тип индекса. Дополнительные сведения о вводе индексаторов см. в разделе <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>.  
  
<a name="mixing"></a>   
### <a name="mixing-syntaxes"></a>Смешанные синтаксисы  
 Можно смешивать все синтаксисы, показанные выше. Например, ниже приведен пример, создает путь свойства цвет в определенной x, y `ColorGrid` свойство, содержащее массив сетки пикселей <xref:System.Windows.Media.SolidColorBrush> объектов:  
  
```xml  
<Rectangle Fill="{Binding ColorGrid[20,30].SolidColorBrushResult}" .../>  
```  
  
### <a name="escapes-for-property-path-strings"></a>Escape-символы для строк путей к свойствам  
 Для некоторых бизнес-объектов может возникнуть случай, когда для правильного анализа строки пути к свойству требуется escape-последовательность. Такая необходимость должна возникать редко, так как многие из этих символов имеют аналогичные проблемы взаимодействия при именовании в языках, которые обычно используются для определения бизнес-объекта.  
  
-   Внутри индексаторов ([ ]) символ каретки (^) служит escape-символом для следующего символа.  
  
-   Необходимо предварять escape-символами (используя XML-сущности) определенные символы, которые являются специальными для определения языка XML. Используйте `&` в качестве escape-символа для символа &. Используйте `>` в качестве escape-символа для символа >.  
  
-   Необходимо предварять escape-символами (с помощью обратной косой черты `\`) символы, которые являются специальными для поведения средства синтаксического анализа WPF XAML для обработки расширения разметки.  
  
    -   Обратная косая черта (`\`) сама по себе является escape-символом.  
  
    -   Знак равенства (`=`) разделяет имя и значение свойства.  
  
    -   Запятая (`,`) разделяет свойства.  
  
    -   Закрывающая фигурная скобка (`}`) — это конец расширения разметки.  
  
> [!NOTE]
>  С технической точки зрения, эти escape-последовательности также работают для пути к свойству раскадровки, но обычно объектные модели обходятся для существующих объектов WPF и использование escape-символов не требуется.  
  
<a name="databinding_sa"></a>   
## <a name="propertypath-for-animation-targets"></a>PropertyPath для целевых объектов анимации  
 Целевое свойство анимации должно быть свойством зависимостей, которое принимает либо <xref:System.Windows.Freezable> или типом-примитивом. Однако целевое свойство типа и конечное анимированное свойство могут существовать в различных объектах. Для анимаций путь к свойству используется для определения связи между свойством целевого объекта именованной анимации и заданным целевым свойством анимации путем обхода отношений "объект/свойство" в значениях свойств.  
  
<a name="general"></a>   
### <a name="general-object-property-considerations-for-animations"></a>Общие рекомендации для отношений "объект/свойство" для анимаций  
 Подробнее о концепциях анимации в целом см. в разделах [Общие сведения о раскадровке ](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md) и [Общие сведения об анимации ](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Тип значения или анимируемого свойства должно равняться <xref:System.Windows.Freezable> типа или простому типу. Свойство, которое запускает путь должен определять имя свойства зависимостей, который существует в указанном <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> типа.  
  
 Для поддержки клонирования для анимации <xref:System.Windows.Freezable> , уже заморожена, объекта, заданного параметром <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> должно быть <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> производного класса.  
  
<a name="singlestepanim"></a>   
### <a name="single-property-on-the-target-object"></a>Одно свойство в целевом объекте  
  
```xml  
<animation Storyboard.TargetProperty="propertyName" .../>  
```  
  
 `propertyName` необходимо разрешить имя свойства зависимостей, который существует в указанном <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> типа.  
  
<a name="indirectanim"></a>   
### <a name="indirect-property-targeting"></a>Косвенное назначение свойства  
  
```xml  
<animation Storyboard.TargetProperty="propertyName.propertyName2" .../>  
```  
  
 `propertyName` должно быть свойством, либо <xref:System.Windows.Freezable> тип значения или примитив, который существует в указанном <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> типа.  
  
 `propertyName2` должно быть именем свойства зависимостей, существующего в объекте, который является значением `propertyName`. Другими словами `propertyName2` должны существовать в качестве свойства зависимостей для типа, `propertyName` <xref:System.Windows.DependencyProperty.PropertyType%2A>.  
  
 Косвенное назначение анимации необходимо из-за примененных стилей и шаблонов. Для целевого объекта анимации требуется <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> на целевой объект, а имя устанавливается с помощью [x: Name](../../../../docs/framework/xaml-services/x-name-directive.md) или <xref:System.Windows.FrameworkElement.Name%2A>. Хотя элементы шаблона и стиля также могут иметь имена, эти имена действительны только в области имен стиля и шаблона. (Если бы шаблоны и стили совместно использовали пространства имен с разметкой приложения, имена не могли бы быть уникальными. Стили и шаблоны буквально разделяются между экземплярами и могут сохранять повторяющиеся имена). Таким образом, если отдельные свойства элемента, которые нужно анимировать, исходят из стиля или шаблона, то нужно начать с именованного экземпляра элемента, который не происходит из шаблона стиля. Затем укажите целевой объект в визуальном дереве стиля или шаблона, чтобы достичь свойства, которое нужно анимировать.  
  
 Например <xref:System.Windows.Controls.Panel.Background%2A> свойство <xref:System.Windows.Controls.Panel> завершения <xref:System.Windows.Media.Brush> (фактически <xref:System.Windows.Media.SolidColorBrush>), поступивший из шаблона темы. Для анимации <xref:System.Windows.Media.Brush> полностью, то потребуется BrushAnimation (возможно, один для каждого <xref:System.Windows.Media.Brush> типа) и тип отсутствует. Для анимации кисти, вместо анимации свойств конкретного <xref:System.Windows.Media.Brush> типа. Вам необходимо получить из <xref:System.Windows.Media.SolidColorBrush> для его <xref:System.Windows.Media.SolidColorBrush.Color%2A> для применения <xref:System.Windows.Media.Animation.ColorAnimation> существует. Путь к свойству в этом примере будет `Background.Color`.  
  
<a name="attachedanim"></a>   
### <a name="attached-properties"></a>Вложенные свойства  
  
```xml  
<animation Storyboard.TargetProperty="(ownerType.propertyName)" .../>  
```  
  
 Скобки указывают, что это свойство в <xref:System.Windows.PropertyPath> должен быть создан с помощью частичного уточнения. Для поиска типа может использоваться пространство имен XML. `ownerType` Поиск типов, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор имеет доступ, с помощью <xref:System.Windows.Markup.XmlnsDefinitionAttribute> объявления в каждой сборке. В большинстве приложений есть пространство имен XML по умолчанию, сопоставленное пространству имен [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)], поэтому префикс обычно требуется только для настраиваемых типов или типов вне этого пространства имен. `propertyName` должно разрешаться как имя свойства, существующего в `ownerType`. Свойство, указанное как `propertyName` должен быть <xref:System.Windows.DependencyProperty>. (Все присоединенные свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализуются как свойства взаимозависимостей, поэтому эта проблема возникает только для настраиваемых присоединенных свойств.)  
  
<a name="indexanim"></a>   
### <a name="indexers"></a>Индексаторы  
  
```xml  
<animation Storyboard.TargetProperty="propertyName.propertyName2[index].propertyName3" .../>  
```  
  
 Большинство свойств зависимостей или <xref:System.Windows.Freezable> типы не поддерживают индексатора. Таким образом, единственное использование индексатора в пути к анимации — это промежуточное положение между свойством, которое запускает цепочку в именованном целевом объекте и конечным анимированным свойством. В предоставленном синтаксисе это `propertyName2`. Например, на использование индексатора необходимость может возникнуть при промежуточного свойство является коллекцией, такие как <xref:System.Windows.Media.TransformGroup>, в пути свойства, такие как `RenderTransform.Children[1].Angle`.  
  
<a name="ppincode"></a>   
## <a name="propertypath-in-code"></a>PropertyPath в коде  
 Использование кода <xref:System.Windows.PropertyPath>, включая создание <xref:System.Windows.PropertyPath>, описаны в разделах, относящихся к <xref:System.Windows.PropertyPath>.  
  
 В общем случае <xref:System.Windows.PropertyPath> предназначен для использования двух различных конструкторов, один для привязки и простого применения анимации и один для применения сложной анимации. Используйте <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> подпись для привязки варианты использования, где объект — строка. Используйте <xref:System.Windows.PropertyPath.%23ctor%28System.Object%29> подписи для путей устанавливаются анимации, когда этот объект является <xref:System.Windows.DependencyProperty>. Используйте <xref:System.Windows.PropertyPath.%23ctor%28System.String%2CSystem.Object%5B%5D%29> подпись для сложных анимации. Последний конструктор использует строку токена для первого параметра и массив объектов, которые заполняют позиции в строке токена, чтобы определить отношение пути к свойству.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.PropertyPath>  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Общие сведения о раскадровке](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
