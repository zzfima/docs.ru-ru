---
title: "Расширение разметки RelativeSource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ea5d269c3d455a4fbe3a34dca4335e0d8999d80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="relativesource-markupextension"></a>Расширение разметки RelativeSource
Задает свойства <xref:System.Windows.Data.RelativeSource> источника привязки, которые должны использоваться в [расширение разметки со связыванием](../../../../docs/framework/wpf/advanced/binding-markup-extension.md), или при задании <xref:System.Windows.Data.Binding.RelativeSource%2A> свойство <xref:System.Windows.Data.Binding> элемента установлено в XAML.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xml  
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>  
```  
  
## <a name="xaml-attribute-usage-nested-within-binding-extension"></a>Использование атрибута XAML (вложенный в расширение Binding)  
  
```xml  
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML  
  
```xml  
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource Mode="modeEnumValue"/>  
  </Binding.RelativeSource>  
</Binding>  
- or   
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource  
      Mode="FindAncestor"  
      AncestorType="{x:Type typeName}"  
      AncestorLevel="intLevel"  
    />  
  </Binding.RelativeSource>  
</Binding>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`modeEnumValue`|Один из следующих вариантов:<br /><br /> -Символ строки `Self`; соответствует <xref:System.Windows.Data.RelativeSource> , созданных с помощью его <xref:System.Windows.Data.RelativeSource.Mode%2A> свойство <xref:System.Windows.Data.RelativeSourceMode.Self>.<br />-Символ строки `TemplatedParent`; соответствует <xref:System.Windows.Data.RelativeSource> , созданных с помощью его <xref:System.Windows.Data.RelativeSource.Mode%2A> свойство <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.<br />-Символ строки `PreviousData`; соответствует <xref:System.Windows.Data.RelativeSource> , созданных с помощью его <xref:System.Windows.Data.RelativeSource.Mode%2A> свойство <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.<br />-Сведения см. ниже в `FindAncestor` режиме.|  
|`FindAncestor`|Строковая лексема `FindAncestor`. Использовании этой лексемы осуществляет переход в режим, где `RelativeSource` задает тип предка и (при необходимости) уровень предка. Это соответствует <xref:System.Windows.Data.RelativeSource> при создании со свойством <xref:System.Windows.Data.RelativeSource.Mode%2A>, для которого задано значение <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.|  
|`typeName`|Требуется для режима `FindAncestor`. Имя типа, которое заполняет свойство <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.|  
|`intLevel`|Необязательно для режима `FindAncestor`. Уровень предка (вычисляется в направлении родителя в логическом дереве).|  
  
## <a name="remarks"></a>Примечания  
 `{RelativeSource TemplatedParent}`Использование привязки являются ключевым способом, направленный большего концепции разделения элемента управления пользовательского интерфейса и логики управления. Это делает возможным привязку из определения шаблона к созданному по шаблону родительскому элементу (экземпляр объекта времени выполнения, в котором применяется шаблон). В этом случае [расширения разметки TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) на самом деле является сокращением для следующее выражение привязки: `{Binding RelativeSource={RelativeSource TemplatedParent}}`. `TemplateBinding`или `{RelativeSource TemplatedParent}` использований присутствуют только соответствующие в XAML, определяющего шаблона. Дополнительные сведения см. в разделе [расширения разметки TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)  
  
 `{RelativeSource FindAncestor}`основном применяется в шаблонах элементов управления или прогнозируемого самодостаточным пользовательского интерфейса композиции, для случаев, когда элемент управления всегда должен быть в визуальное дерево определенного типа предка. Например, элементы в элементе управления элементами могут использовать вхождения `FindAncestor` для привязки к свойствам предка элемента управления элементами. Либо элементы, которые являются частью композиции элемента управления в шаблоне, могут использовать привязки `FindAncestor` к родительским элементам в той же структуре композиции.  
  
 В синтаксисе объектного элемента для режима `FindAncestor`, показанного выше в разделах синтаксиса XAML, второй синтаксис объектного элемента используется специально для режима `FindAncestor`. Режим `FindAncestor` требует значения <xref:System.Windows.Data.RelativeSource.AncestorType%2A>. Необходимо задать <xref:System.Windows.Data.RelativeSource.AncestorType%2A> как атрибут с использованием [расширение разметки x: Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md) ссылку на тип предка. Значение <xref:System.Windows.Data.RelativeSource.AncestorType%2A> используется при обработке запроса привязки во время выполнения.  
  
 Для режима `FindAncestor` необязательное свойство <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> может помочь устранить неоднозначность поиска предка в случаях, где в дереве элементов, возможно, существует более одного предка данного типа.  
  
 Дополнительные сведения об использовании режима `FindAncestor` см. в разделе <xref:System.Windows.Data.RelativeSource>.  
  
 `{RelativeSource Self}`полезно для сценариев, где одно свойство экземпляра должно зависеть от значения другого свойства тот же экземпляр и отношение зависимостей общие свойства (например, приведение) уже существует между этими двумя свойствами. Несмотря на то, что довольно редко, что существует два свойства для объекта таким образом, что значения идентичны буквально (и идентично типизированы), можно также применить `Converter` параметр привязку, которая имеет `{RelativeSource Self}`и использовать преобразователь для преобразования между исходной и типы целевых объектов. Другим случаем `{RelativeSource Self}` как часть <xref:System.Windows.MultiDataTrigger>.  
  
 Например, следующий код XAML определяет такой элемент <xref:System.Windows.Shapes.Rectangle>, что независимо от того, какое значение вводится для свойства <xref:System.Windows.FrameworkElement.Width%2A>, объектом <xref:System.Windows.Shapes.Rectangle> всегда является квадрат: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`  
  
 `{RelativeSource PreviousData}`используется в шаблонах данных или в случаях, где привязки использование коллекции в качестве источника данных. Можно использовать `{RelativeSource PreviousData}` для выделения связи между элементами смежных набора данных в коллекции. Соответствующей методикой является установление привязки <xref:System.Windows.Data.MultiBinding> между текущим и предыдущим элементами в источнике данных и использование преобразователя в этой привязке для определения различия между двумя элементами и их свойствами.  
  
 В следующем примере первый элемент <xref:System.Windows.Controls.TextBlock> в шаблоне элементов отображает текущий номер. Второй <xref:System.Windows.Controls.TextBlock> привязка <xref:System.Windows.Data.MultiBinding> , обычно общедоступны имеет два <xref:System.Windows.Data.Binding> consistuents: текущей записи и привязку, которая намеренно использует предыдущей записи данных с помощью `{RelativeSource PreviousData}`. Затем преобразователь в объекте <xref:System.Windows.Data.MultiBinding> вычисляет разницу и возвращает ее в привязку.  
  
```xml  
<ListBox Name="fibolist">  
    <ListBox.ItemTemplate>  
        <DataTemplate>  
            <StackPanel Orientation="Horizontal">  
            <TextBlock Text="{Binding}"/>  
            <TextBlock>, difference = </TextBlock>  
                <TextBlock>  
                    <TextBlock.Text>  
                        <MultiBinding Converter="{StaticResource DiffConverter}">  
                            <Binding/>  
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>  
                        </MultiBinding>  
                    </TextBlock.Text>  
                </TextBlock>  
            </StackPanel>  
        </DataTemplate>  
    </ListBox.ItemTemplate>  
```  
  
 Описание привязки данных, как концепции здесь, не описаны в разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализации процессора XAML, обработка для данного расширения разметки определяется <xref:System.Windows.Data.RelativeSource> класса.  
  
 `RelativeSource` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в XAML используют `{` и `}` символов в синтаксисе их атрибутов, который является соглашением, по которому обработчик XAML узнает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Data.Binding>  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Общие сведения об объявлении привязок](../../../../docs/framework/wpf/data/binding-declarations-overview.md)  
 [Расширение разметки x:Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md)
