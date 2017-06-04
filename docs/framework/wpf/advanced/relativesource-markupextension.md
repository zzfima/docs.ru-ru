---
title: "Расширение разметки RelativeSource | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RelativeSource"
helpviewer_keywords: 
  - "RelativeSource - расширения разметки"
  - "XAML, RelativeSource - расширение разметки"
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Расширение разметки RelativeSource
Задает свойства источника привязки <xref:System.Windows.Data.RelativeSource> для использования внутри [Привязка расширения разметки](../../../../docs/framework/wpf/advanced/binding-markup-extension.md), или при задании свойства <xref:System.Windows.Data.Binding.RelativeSource%2A> элемента <xref:System.Windows.Data.Binding>, определенного в XAML.  
  
## Использование атрибута XAML  
  
```  
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>  
```  
  
## Использование атрибута XAML \(вложенный в расширение Binding\)  
  
```  
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>  
```  
  
## Использование элемента объекта XAML  
  
```  
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource Mode="modeEnumValue"/>  
  </Binding.RelativeSource>  
</Binding>  
- or   
<Binding>  
  <Binding.RelativeSource>  
    <RelativeSource  
      Mode="FindAncestor"  
      AncestorType="{x:Type typeName}"  
      AncestorLevel="intLevel"  
    />  
  </Binding.RelativeSource>  
</Binding>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`modeEnumValue`|Один из следующих вариантов:<br /><br /> -   Строковая лексема `Self`; соответствует <xref:System.Windows.Data.RelativeSource> при создании со свойством <xref:System.Windows.Data.RelativeSource.Mode%2A>, для которого установлено значение <xref:System.Windows.Data.RelativeSourceMode>.<br />-   Строковая лексема `TemplatedParent`; соответствует <xref:System.Windows.Data.RelativeSource> при создании со свойством <xref:System.Windows.Data.RelativeSource.Mode%2A>, для которого установлено значение <xref:System.Windows.Data.RelativeSourceMode>.<br />-   Строковая лексема `PreviousData`; соответствует <xref:System.Windows.Data.RelativeSource> при создании со свойством <xref:System.Windows.Data.RelativeSource.Mode%2A>, для которого установлено значение <xref:System.Windows.Data.RelativeSourceMode>.<br />-   Сведения о режиме `FindAncestor` приведены ниже.|  
|`FindAncestor`|Строковая лексема `FindAncestor`.  Использовании этой лексемы осуществляет переход в режим, где `RelativeSource` задает тип предка и \(при необходимости\) уровень предка.  Это соответствует <xref:System.Windows.Data.RelativeSource> при создании со свойством <xref:System.Windows.Data.RelativeSource.Mode%2A>, для которого задано значение <xref:System.Windows.Data.RelativeSourceMode>.|  
|`typeName`|Требуется для режима `FindAncestor`.  Имя типа, которое заполняет свойство <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.|  
|`intLevel`|Необязательно для режима `FindAncestor`.  Уровень предка \(вычисляется в направлении родителя в логическом дереве\).|  
  
## Заметки  
 Использование привязки `{RelativeSource TemplatedParent}` является основным механизмом решения масштабной задачи разделения пользовательского интерфейса элемента управления и логики элемента управления.  Это делает возможным привязку из определения шаблона к созданному по шаблону родительскому элементу \(экземпляр объекта времени выполнения, в котором применяется шаблон\).  В этом случае [Расширение разметки TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) фактически является сокращением для следующего выражения привязки: `{Binding RelativeSource={RelativeSource TemplatedParent}}`.  Использование `TemplateBinding` или `{RelativeSource TemplatedParent}` имеет значение только в коде XAML, где определяется шаблон.  Дополнительные сведения см. в разделе [Расширение разметки TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md).  
  
 `{RelativeSource FindAncestor}` используется главным образом в шаблонах элементов управления или предсказуемых автономных композициях пользовательского интерфейса в случаях, когда элемент управления всегда должен находиться в видимом дереве определенного типа предка.  Например, элементы в элементе управления элементами могут использовать вхождения `FindAncestor` для привязки к свойствам предка элемента управления элементами.  Либо элементы, которые являются частью композиции элемента управления в шаблоне, могут использовать привязки `FindAncestor` к родительским элементам в той же структуре композиции.  
  
 В синтаксисе объектного элемента для режима `FindAncestor`, показанного выше в разделах синтаксиса XAML, второй синтаксис объектного элемента используется специально для режима `FindAncestor`.  Режим `FindAncestor` требует значения <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.  Необходимо установить <xref:System.Windows.Data.RelativeSource.AncestorType%2A> в качестве атрибута, используя ссылку [Расширение разметки x:Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md) на тип искомого предка.  Значение <xref:System.Windows.Data.RelativeSource.AncestorType%2A> используется при обработке запроса привязки во время выполнения.  
  
 Для режима `FindAncestor` необязательное свойство <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> может помочь устранить неоднозначность поиска предка в случаях, где в дереве элементов, возможно, существует более одного предка данного типа.  
  
 Дополнительные сведения об использовании режима `FindAncestor` см. в разделе <xref:System.Windows.Data.RelativeSource>.  
  
 `{RelativeSource Self}` удобно использовать в сценариях, где одно из свойств экземпляра должно зависеть от значения другого свойства того же экземпляра, но между этими двумя свойствами еще не существует общего отношения свойства зависимостей, такого как приведение.  Хотя изредка случается так, что в объекте существует два свойства с буквально одинаковыми значениями \(и идентичными типами\), также можно применить параметр `Converter` к привязке с `{RelativeSource Self}` и использовать этот преобразователь для преобразования из исходного типа в целевой.  Еще один сценарий использования `{RelativeSource Self}` — в составе <xref:System.Windows.MultiDataTrigger>.  
  
 Например, следующий код XAML определяет такой элемент <xref:System.Windows.Shapes.Rectangle>, что независимо от того, какое значение вводится для свойства <xref:System.Windows.FrameworkElement.Width%2A>, объектом <xref:System.Windows.Shapes.Rectangle> всегда является квадрат: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`  
  
 `{RelativeSource PreviousData}` удобно использовать либо в шаблонах данных, либо в случаях, когда привязки используют коллекцию в качестве источника данных.  Можно воспользоваться `{RelativeSource PreviousData}` для выделения связей между соседними элементами данных в коллекции.  Соответствующей методикой является установление привязки <xref:System.Windows.Data.MultiBinding> между текущим и предыдущим элементами в источнике данных и использование преобразователя в этой привязке для определения различия между двумя элементами и их свойствами.  
  
 В следующем примере первый элемент <xref:System.Windows.Controls.TextBlock> в шаблоне элементов отображает текущий номер.  Вторая привязка <xref:System.Windows.Controls.TextBlock> является привязкой <xref:System.Windows.Data.MultiBinding>, которая номинально состоит из двух частей <xref:System.Windows.Data.Binding>: текущей записи и привязки, в которой намеренно используется предыдущая запись данных с помощью `{RelativeSource PreviousData}`.  Затем преобразователь в объекте <xref:System.Windows.Data.MultiBinding> вычисляет разницу и возвращает ее в привязку.  
  
```  
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
  
 Описание принципа привязки данных не рассматривается в данном разделе; см. [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 В реализации обработчика XAML [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обработка данного расширения разметки определяется классом <xref:System.Windows.Data.RelativeSource>.  
  
 `RelativeSource` является расширением разметки.  Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.  Все расширения разметки в XAML используют знаки `{` и `}` в синтаксисе их атрибутов, который является соглашением, по которому обработчик XAML узнает, что расширение разметки должно обработать атрибут.  Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## См. также  
 <xref:System.Windows.Data.Binding>   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Расширения разметки и XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Общие сведения об объявлении привязок](../../../../docs/framework/wpf/data/binding-declarations-overview.md)   
 [Расширение разметки x:Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md)