---
title: Расширение разметки RelativeSource
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: 15fdc9d093bb3efb4ea4cef5d4cdfa8474042f12
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559751"
---
# <a name="relativesource-markupextension"></a>Расширение разметки RelativeSource

Задает свойства источника привязки <xref:System.Windows.Data.RelativeSource>, который будет использоваться в [расширении разметки привязки](binding-markup-extension.md), или при задании свойства <xref:System.Windows.Data.Binding.RelativeSource%2A> элемента <xref:System.Windows.Data.Binding>, установленного в XAML.

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
```

\- или -

```xml
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
|`modeEnumValue`|Возможно одно из следующих:.<br /><br /> — Токен строки `Self`; соответствует <xref:System.Windows.Data.RelativeSource>, созданному со свойством <xref:System.Windows.Data.RelativeSource.Mode%2A>, для которого задано значение <xref:System.Windows.Data.RelativeSourceMode.Self>.<br />— Токен строки `TemplatedParent`; соответствует <xref:System.Windows.Data.RelativeSource>, созданному со свойством <xref:System.Windows.Data.RelativeSource.Mode%2A>, для которого задано значение <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.<br />— Токен строки `PreviousData`; соответствует <xref:System.Windows.Data.RelativeSource>, созданному со свойством <xref:System.Windows.Data.RelativeSource.Mode%2A>, для которого задано значение <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.<br />Дополнительные сведения о режиме `FindAncestor` см. ниже.|
|`FindAncestor`|Строковая лексема `FindAncestor`. Использовании этой лексемы осуществляет переход в режим, где `RelativeSource` задает тип предка и (при необходимости) уровень предка. Это соответствует <xref:System.Windows.Data.RelativeSource> при создании со свойством <xref:System.Windows.Data.RelativeSource.Mode%2A>, для которого задано значение <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.|
|`typeName`|Требуется для режима `FindAncestor`. Имя типа, которое заполняет свойство <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.|
|`intLevel`|Необязательно для режима `FindAncestor`. Уровень предка (вычисляется в направлении родителя в логическом дереве).|

## <a name="remarks"></a>Заметки

`{RelativeSource TemplatedParent}` использования привязки являются ключевой методикой, которая устраняет большую концепцию разделения пользовательского интерфейса элемента управления и логики элемента управления. Это делает возможным привязку из определения шаблона к созданному по шаблону родительскому элементу (экземпляр объекта времени выполнения, в котором применяется шаблон). В этом случае [расширение разметки TemplateBinding](templatebinding-markup-extension.md) на самом деле является сокращением для следующего выражения привязки: `{Binding RelativeSource={RelativeSource TemplatedParent}}`. `TemplateBinding` и `{RelativeSource TemplatedParent}` используются только в коде XAML, определяющем шаблон. Дополнительные сведения см. в разделе [расширение разметки TemplateBinding](templatebinding-markup-extension.md).

`{RelativeSource FindAncestor}` в основном используется в шаблонах элементов управления или предсказуемых самостоятельных композициях пользовательского интерфейса, в случаях, когда элемент управления всегда должен находиться в визуальном дереве определенного типа предка. Например, элементы в элементе управления элементами могут использовать вхождения `FindAncestor` для привязки к свойствам предка элемента управления элементами. Либо элементы, которые являются частью композиции элемента управления в шаблоне, могут использовать привязки `FindAncestor` к родительским элементам в той же структуре композиции.

В синтаксисе объектного элемента для режима `FindAncestor`, показанного выше в разделах синтаксиса XAML, второй синтаксис объектного элемента используется специально для режима `FindAncestor`. Режим `FindAncestor` требует значения <xref:System.Windows.Data.RelativeSource.AncestorType%2A>. Необходимо задать <xref:System.Windows.Data.RelativeSource.AncestorType%2A> как атрибут, используя ссылку на [расширение разметки x:Type](../../../desktop-wpf/xaml-services/xtype-markup-extension.md) в качестве типа предка для поиска. Значение <xref:System.Windows.Data.RelativeSource.AncestorType%2A> используется при обработке запроса привязки во время выполнения.

Для режима `FindAncestor` необязательное свойство <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> может помочь устранить неоднозначность поиска предка в случаях, где в дереве элементов, возможно, существует более одного предка данного типа.

Дополнительные сведения об использовании режима `FindAncestor` см. в разделе <xref:System.Windows.Data.RelativeSource>.

`{RelativeSource Self}` удобно использовать в сценариях, где одно свойство экземпляра должно зависеть от значения другого свойства того же экземпляра, и не существует общей связи свойств зависимости (например, приведения) между этими двумя свойствами. Несмотря на то, что в объекте присутствуют два свойства, в которых значения буквально идентичны (и идентичны), можно также применить параметр `Converter` к привязке, которая имеет `{RelativeSource Self}`, и использовать преобразователь для преобразования между исходным и целевым типами. Другой сценарий для `{RelativeSource Self}` является частью <xref:System.Windows.MultiDataTrigger>.

Например, следующий код XAML определяет такой элемент <xref:System.Windows.Shapes.Rectangle>, что независимо от того, какое значение вводится для свойства <xref:System.Windows.FrameworkElement.Width%2A>, объектом <xref:System.Windows.Shapes.Rectangle> всегда является квадрат: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`

`{RelativeSource PreviousData}` можно использовать либо в шаблонах данных, либо в случаях, когда привязки используют коллекцию в качестве источника данных. `{RelativeSource PreviousData}` можно использовать для выделения связей между соседними элементами данных в коллекции. Соответствующей методикой является установление привязки <xref:System.Windows.Data.MultiBinding> между текущим и предыдущим элементами в источнике данных и использование преобразователя в этой привязке для определения различия между двумя элементами и их свойствами.

В следующем примере первый элемент <xref:System.Windows.Controls.TextBlock> в шаблоне элементов отображает текущий номер. Вторая привязка <xref:System.Windows.Controls.TextBlock> является <xref:System.Windows.Data.MultiBinding>, которая в номинальном случае имеет два <xref:System.Windows.Data.Binding> составляющих: текущую запись и привязку, намеренно использующую предыдущую запись данных с помощью `{RelativeSource PreviousData}`. Затем преобразователь в объекте <xref:System.Windows.Data.MultiBinding> вычисляет разницу и возвращает ее в привязку.

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

Описание привязки данных в качестве концепции не рассматривается здесь, см. в разделе [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md).

В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализации процессора XAML обработка этого расширения разметки определяется классом <xref:System.Windows.Data.RelativeSource>.

`RelativeSource` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. Все расширения разметки в XAML используют `{` и `}` символов в синтаксисе атрибутов, который является соглашением, по которому обработчик XAML распознает, что расширение разметки должно обработать атрибут. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Data.Binding>
- [Стилизация и использование шаблонов](../controls/styling-and-templating.md)
- [Общие сведения о языке XAML (WPF)](xaml-overview-wpf.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Общие сведения об объявлении привязок](../data/binding-declarations-overview.md)
- [Расширение разметки x:Type](../../../desktop-wpf/xaml-services/xtype-markup-extension.md)
