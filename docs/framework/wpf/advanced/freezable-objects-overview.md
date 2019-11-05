---
title: Общие сведения об объектах класса Freezable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], description
- unfreezing Freezable objects [WPF]
- classes [WPF], Freezable
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
ms.openlocfilehash: 755240859829042e9790b9c89e47bb7a2013ceef
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460445"
---
# <a name="freezable-objects-overview"></a>Общие сведения об объектах класса Freezable

В этом разделе описывается эффективное использование и создание объектов <xref:System.Windows.Freezable>, которые предоставляют специальные функции, которые могут помочь повысить производительность приложения. Примерами объектов Freezable являются кисти, перья, преобразования, геометрические объекты и анимация.

<a name="whatisafreezable"></a>

## <a name="what-is-a-freezable"></a>Что такое Freezable?

<xref:System.Windows.Freezable> — это особый тип объекта с двумя состояниями: незамороженный и замороженный. Если не заморозить, то поведение <xref:System.Windows.Freezable> выглядит как любой другой объект. После заморозки <xref:System.Windows.Freezable> больше не может быть изменена.

<xref:System.Windows.Freezable> предоставляет событие <xref:System.Windows.Freezable.Changed> для уведомления наблюдателей о любых изменениях в объекте. Замораживание <xref:System.Windows.Freezable> может повысить его производительность, так как больше не требуется тратить ресурсы на уведомления об изменениях. Замороженные <xref:System.Windows.Freezable> также можно совместно использовать в потоках, в то время как незамороженный <xref:System.Windows.Freezable> не может.

Несмотря на то, что класс <xref:System.Windows.Freezable> содержит много приложений, большинство <xref:System.Windows.Freezable> объектов в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] связаны с графической подсистемой.

Класс <xref:System.Windows.Freezable> упрощает использование определенных объектов графической системы и помогает повысить производительность приложений. Примерами типов, которые наследуют от <xref:System.Windows.Freezable>, являются классы <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>и <xref:System.Windows.Media.Geometry>. Поскольку они содержат неуправляемые ресурсы, система должна отслеживать эти объекты для внесения изменений, а затем обновлять соответствующие неуправляемые ресурсы при изменении исходного объекта. Даже если вы не изменяете объект графической системы, система должна по-прежнему тратить некоторые ресурсы на наблюдение за объектом, если вы его изменяете.

Например, предположим, что вы создаете кисть <xref:System.Windows.Media.SolidColorBrush> и используете ее для рисования фона кнопки.

[!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
[!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]

При отображении кнопки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] графическая подсистема использует предоставленные сведения для рисования группы пикселей, чтобы создать внешний вид кнопки. Несмотря на то, что для описания того, как должна быть окрашена кнопка, используется сплошная Цветная кисть, сплошная цветовая кисть не выполняет рисование. Графическая система создает быстрые низкоуровневые объекты для кнопки и кисти, и это объекты, которые фактически отображаются на экране.

Если вы изменили кисть, эти низкоуровневые объекты пришлось бы повторно создать. Класс Freezable дает кисти возможность находить соответствующие созданные объекты низкого уровня и обновлять их при изменении. Если эта возможность включена, кисть называется «незамороженной».

Метод <xref:System.Windows.Freezable.Freeze%2A> Freezable позволяет отключить эту возможность самостоятельного обновления. Этот метод можно использовать, чтобы сделать кисть замороженной или неизменяемой.

> [!NOTE]
> Не каждый объект Freezable может быть заморожен. Чтобы избежать возникновения <xref:System.InvalidOperationException>, проверьте значение свойства <xref:System.Windows.Freezable.CanFreeze%2A> объекта Freezable, чтобы определить, можно ли его заморозить перед попыткой его заморозить.

[!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
[!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]

Если вам больше не нужно изменять Freezable, замораживание обеспечивает преимущества производительности. Если вы захотите заморозить кисть в этом примере, графической системе больше не потребуется отслеживать изменения. Графическая система также может выполнять другие оптимизации, так как она знает, что кисть не изменится.

> [!NOTE]
> Для удобства объекты Freezable остаются незафиксированными, если их явно не заморозить.

<a name="frozenfreezables"></a>

## <a name="using-freezables"></a>Использование Freezable

Использование незамороженного объекта Freezable аналогично использованию любого другого типа объектов. В следующем примере цвет <xref:System.Windows.Media.SolidColorBrush> меняется с желтого на красный после того, как он используется для рисования фона кнопки. Графическая система работает в фоновом режиме для автоматического изменения кнопки с желтого на красную при следующем обновлении экрана.

[!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
[!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]

### <a name="freezing-a-freezable"></a>Замораживание Freezable

Чтобы сделать <xref:System.Windows.Freezable> неизменяемым, вызовите его метод <xref:System.Windows.Freezable.Freeze%2A>. При замораживании объекта, содержащего объекты Freezable, эти объекты также фиксируются. Например, если заморозить <xref:System.Windows.Media.PathGeometry>, содержащиеся в нем данные и сегменты будут зафиксированы.

Freezable **нельзя** зафиксировать, если выполняется одно из следующих условий.

- Он имеет анимированные или привязанные к данным свойства.

- Он имеет свойства, заданные динамическим ресурсом. (Дополнительные сведения о динамических ресурсах см. в разделе [ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) .)

- Он содержит <xref:System.Windows.Freezable> подобъекты, которые не могут быть заморожены.

Если эти условия имеют значение false и вы не собираетесь изменять <xref:System.Windows.Freezable>, следует закрепить его, чтобы получить выигрыш в производительности, описанный выше.

После вызова метода <xref:System.Windows.Freezable.Freeze%2A> Freezable его нельзя изменить. Попытка изменить зафиксированный объект приводит к возникновению <xref:System.InvalidOperationException>. Следующий код вызывает исключение, так как пытается изменить кисть после ее замораживания.

[!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
[!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]

Чтобы избежать возникновения этого исключения, можно использовать метод <xref:System.Windows.Freezable.IsFrozen%2A>, чтобы определить, заморожен ли <xref:System.Windows.Freezable>.

[!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
[!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]

В предыдущем примере кода была сделана изменяемая копия зафиксированного объекта с помощью метода <xref:System.Windows.Freezable.Clone%2A>. В следующем разделе приводятся более подробные сведения о клонировании.

> [!NOTE]
> Поскольку зафиксированное Freezable не может быть анимированным, система анимации автоматически создает изменяемые клоны зафиксированных <xref:System.Windows.Freezable> объектов при попытке анимировать их с помощью <xref:System.Windows.Media.Animation.Storyboard>. Чтобы устранить издержки производительности, вызванные клонированием, оставьте объект незамороженным, если вы планируете его анимировать. Дополнительные сведения об анимации с помощью раскадровок см. в разделе [Общие сведения о раскадровках](../graphics-multimedia/storyboards-overview.md).

### <a name="freezing-from-markup"></a>Замораживание из разметки

Для закрепления объекта <xref:System.Windows.Freezable>, объявленного в разметке, используется атрибут `PresentationOptions:Freeze`. В следующем примере <xref:System.Windows.Media.SolidColorBrush> объявляется как ресурс страницы и зафиксирован. Затем он используется для задания фона кнопки.

[!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]

Чтобы использовать атрибут `Freeze`, необходимо выполнить преобразование в пространство имен "Параметры представления": `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`. `PresentationOptions` является рекомендуемым префиксом для сопоставления этого пространства имен:

```xaml
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"
```

Так как не все читатели XAML распознают этот атрибут, рекомендуется использовать [атрибут MC: Ignorable](mc-ignorable-attribute.md) , чтобы пометить атрибут `Presentation:Freeze` как игнорируемый:

```xaml
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
mc:Ignorable="PresentationOptions"
```

Дополнительные сведения см. на странице [MC: Ignorable Attribute](mc-ignorable-attribute.md) .

### <a name="unfreezing-a-freezable"></a>"Unfreezingе" Freezable

После замораживания <xref:System.Windows.Freezable> не может быть изменена или незаморожена. Однако можно создать незамороженный клон с помощью метода <xref:System.Windows.Freezable.Clone%2A> или <xref:System.Windows.Freezable.CloneCurrentValue%2A>.

В следующем примере фон кнопки задается кистью, а кисть заморожена. При помощи метода <xref:System.Windows.Freezable.Clone%2A> выполняется незамороженная копия кисти. Клон изменяется и используется для изменения фона кнопки с желтого на красный.

[!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
[!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]

> [!NOTE]
> Независимо от того, какой метод клонирования вы используете, анимации никогда не копируются в новый <xref:System.Windows.Freezable>.

Методы <xref:System.Windows.Freezable.Clone%2A> и <xref:System.Windows.Freezable.CloneCurrentValue%2A> создают глубокие копии объекта Freezable. Если объект Freezable содержит другие замороженные объекты Freezable, они также копируются и становятся изменяемыми. Например, при клонировании зафиксированной <xref:System.Windows.Media.PathGeometry>, чтобы сделать его изменяемым, содержащиеся в нем данные и рисунки также копируются и становятся изменяемыми.

<a name="createyourownfreezableclass"></a>

## <a name="creating-your-own-freezable-class"></a>Создание собственного класса Freezable

Класс, производный от <xref:System.Windows.Freezable>, получает следующие функции.

- Особые состояния: доступное только для чтения (зафиксированное) и состояние с возможностью записи.

- Потокобезопасность. замороженная <xref:System.Windows.Freezable> может совместно использоваться несколькими потоками.

- Подробное уведомление об изменении. в отличие от других <xref:System.Windows.DependencyObject>, объекты Freezable предоставляют уведомления об изменениях при изменении значений подсвойств.

- Простое клонирование: класс Freezable уже реализовал несколько методов, создающих глубокие клоны.

<xref:System.Windows.Freezable> является типом <xref:System.Windows.DependencyObject>и, следовательно, использует систему свойств зависимостей. Свойства класса не обязательно должны быть свойствами зависимостей, но использование свойств зависимости уменьшит объем кода, который необходимо написать, так как класс <xref:System.Windows.Freezable> был разработан с учетом свойств зависимостей. Дополнительные сведения о системе свойств зависимостей см. в разделе [Общие сведения о свойствах зависимостей](dependency-properties-overview.md).

Каждый подкласс <xref:System.Windows.Freezable> должен переопределять метод <xref:System.Windows.Freezable.CreateInstanceCore%2A>. Если ваш класс использует свойства зависимостей для всех своих данных, то все готово.

Если класс содержит элементы данных, не относящиеся к свойствам зависимостей, необходимо также переопределить следующие методы.

- <xref:System.Windows.Freezable.CloneCore%2A>

- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>

- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>

- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>

- <xref:System.Windows.Freezable.FreezeCore%2A>

Также необходимо соблюдать следующие правила доступа к элементам данных и их записи, которые не являются свойствами зависимостей.

- В начале любого API, считывающего члены данных, не относящиеся к свойствам зависимостей, вызовите метод <xref:System.Windows.Freezable.ReadPreamble%2A>.

- В начале любого API, который записывает члены данных, не относящиеся к свойствам зависимостей, вызовите метод <xref:System.Windows.Freezable.WritePreamble%2A>. (После вызова <xref:System.Windows.Freezable.WritePreamble%2A> в API-интерфейсе не нужно выполнять дополнительный вызов <xref:System.Windows.Freezable.ReadPreamble%2A>, если также считываются члены данных, не являющиеся свойствами зависимостей.)

- Вызовите метод <xref:System.Windows.Freezable.WritePostscript%2A> перед выходом методов, которые выполняют запись в члены данных свойств, не являющихся зависимостями.

Если класс содержит элементы данных, не являющиеся свойствами зависимости, которые являются <xref:System.Windows.DependencyObject> объектами, необходимо также вызвать метод <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> при каждом изменении одного из значений, даже если вы настраиваете элемент на `null`.

> [!NOTE]
> Очень важно начинать каждый <xref:System.Windows.Freezable> метод, переопределяемый с помощью вызова базовой реализации.

Пример настраиваемого класса <xref:System.Windows.Freezable> см. в разделе [Пример пользовательской анимации](https://go.microsoft.com/fwlink/?LinkID=159981).

## <a name="see-also"></a>См. также

- <xref:System.Windows.Freezable>
- [Пример пользовательской анимации](https://go.microsoft.com/fwlink/?LinkID=159981)
- [Общие сведения о свойствах зависимости](dependency-properties-overview.md)
- [Пользовательские свойства зависимостей](custom-dependency-properties.md)
