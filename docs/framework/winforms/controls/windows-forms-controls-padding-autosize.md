---
title: Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств Padding, Margins и AutoSize
ms.date: 03/30/2017
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: daf0c6495b89033e75c27a1ff0cbceaff9d85f34
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987168"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a>Пошаговое руководство. Размещение элементов управления с заполнением, полями и свойством AutoSize

Точное расположение элементов управления на форме является важным для многих приложений. **Конструктор Windows Forms** в Visual Studio предоставляет множество инструментов макета для решения этой задачи. Три наиболее важных свойства: <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>и <xref:System.Windows.Forms.Control.AutoSize%2A> , которые имеются во всех элементах управления Windows Forms.

Свойство <xref:System.Windows.Forms.Control.Margin%2A> определяет поле вокруг элемента управления, благодаря которому обеспечивается определенное расстояние между границами этого элемента и другими элементами.

Свойство <xref:System.Windows.Forms.Control.Padding%2A> определяет поле внутри элемента управления, благодаря которому обеспечивается определенное расстояние между содержимым элемента управления (например, значением свойства <xref:System.Windows.Forms.Control.Text%2A>) и его границами.

На рисунке ниже демонстрируется значение свойств <xref:System.Windows.Forms.Control.Padding%2A> и <xref:System.Windows.Forms.Control.Margin%2A> элемента управления.

![Поля и заполнение для элементов управления Windows Forms](./media/vs-winformpadmargin.gif)

<xref:System.Windows.Forms.Control.AutoSize%2A> Свойство указывает элементу управления на автоматическое изменение размера в соответствии с его содержимым. Размер не будет меньше, чем значение исходного <xref:System.Windows.Forms.Control.Size%2A> свойства, и будет учитывать значение его <xref:System.Windows.Forms.Control.Padding%2A> свойства.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения этого пошагового руководства потребуется Visual Studio.

## <a name="create-the-project"></a>Создание проекта

1. В Visual Studio создайте проект **приложения Windows** с именем `LayoutExample`.

2. Выберите форму в **конструктор Windows Forms**.

## <a name="set-margins-for-controls"></a>Установка полей для элементов управления

Расстояние по умолчанию между элементами управления можно задать с помощью <xref:System.Windows.Forms.Control.Margin%2A> свойства. При перемещении элемента управления, достаточно близкого к другому элементу управления, вы увидите линию привязки, показывающую поля для этих двух элементов управления. Перемещаемый элемент управления также будет привязан к расстоянию, заданному полями.

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a>Размещение элементов управления в форме с помощью свойства Margin

1. Перетащите два <xref:System.Windows.Forms.Button> элемента управления из **панели элементов** в форму.

2. Выберите один из <xref:System.Windows.Forms.Button> элементов управления и переместите его ближе к другому, пока они не будут почти соприкасаются.

   Обратите внимание на линию привязки, которая появляется между ними. Это расстояние является суммой <xref:System.Windows.Forms.Control.Margin%2A> значений двух элементов управления. Перемещаемый элемент управления привязывается к этому расстоянию. Дополнительные сведения см. [в разделе Пошаговое руководство. Упорядочивание элементов управления в Windows Forms с](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)помощью линий привязки.

3. <xref:System.Windows.Forms.Padding.All%2A> <xref:System.Windows.Forms.Control.Margin%2A>Измените свойство одного из элементов управления, развернув запись в окне Свойства и установив для свойства значение 20. <xref:System.Windows.Forms.Control.Margin%2A>

4. Выберите один из <xref:System.Windows.Forms.Button> элементов управления и переместите его ближе к другому.

   Линия привязки, определяющая сумму значений полей, больше, и элемент управления привязывается к большему расстоянию от другого элемента управления.

5. <xref:System.Windows.Forms.Padding.Top%2A> <xref:System.Windows.Forms.Control.Margin%2A>Измените свойство выбранного элемента управления, развернув запись в окне "Свойства" и задав для свойства значение 5. <xref:System.Windows.Forms.Control.Margin%2A>

6. Переместите выбранный элемент управления под другим элементом управления и обратите внимание, что линия привязки короче. Переместите выбранный элемент управления влево от другого элемента управления и обратите внимание, что линия привязки содержит значение, наблюдаемое на шаге 4.

7. Каждому <xref:System.Windows.Forms.Control.Margin%2A> из аспектов <xref:System.Windows.Forms.Padding.All%2A> свойства <xref:System.Windows.Forms.Padding.Left%2A> <xref:System.Windows.Forms.Padding.Right%2A>,, <xref:System.Windows.Forms.Padding.Top%2A> ,<xref:System.Windows.Forms.Padding.Bottom%2A>,, можно присвоить разные значения, или же можно задать для них одно и то же значение со свойством.

## <a name="set-padding-for-controls"></a>Задание заполнения для элементов управления

Чтобы обеспечить точный макет, необходимый для вашего приложения, элементы управления часто будут содержать дочерние элементы управления. Если необходимо указать границу границы дочернего элемента управления для границы родительского элемента управления, используйте <xref:System.Windows.Forms.Control.Padding%2A> свойство родительского элемента управления в сочетании со <xref:System.Windows.Forms.Control.Margin%2A> свойством дочернего элемента управления. Свойство также используется для управления сходством содержимого элемента управления (например <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Text%2A> свойства элемента управления) с его границами. <xref:System.Windows.Forms.Control.Padding%2A>

### <a name="arrange-controls-on-your-form-using-padding"></a>Размещение элементов управления в форме с помощью заполнения

1. Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в свою форму.

2. Измените значение <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.AutoSize%2A> свойства элемента управления на **true**.

3. <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Padding.All%2A>Измените свойство, развернув запись в окне "Свойства" и задав для свойства значение 5. <xref:System.Windows.Forms.Control.Padding%2A>

   Элемент управления расширяется, чтобы предоставить место для нового заполнения.

4. Перетащите элемент управления <xref:System.Windows.Forms.GroupBox> из **панели элементов** в свою форму. Перетащите элемент управления из <xref:System.Windows.Forms.GroupBox> **панели элементов** в элемент управления. <xref:System.Windows.Forms.Button> Разместите <xref:System.Windows.Forms.GroupBox> элемент управления, чтобы он был сброшен в правый нижний угол элемента управления. <xref:System.Windows.Forms.Button>

   Обратите внимание на линии привязки, <xref:System.Windows.Forms.Button> которые отображаются, когда элемент управления приближается к <xref:System.Windows.Forms.GroupBox> нижней и правой границам элемента управления. Эти линии привязки соответствуют <xref:System.Windows.Forms.Control.Margin%2A> свойству <xref:System.Windows.Forms.Button>объекта.

5. <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Padding.All%2A>Измените свойство элементауправления,развернувзаписьвокнеСвойстваиустановивдлясвойствазначение20.<xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Control.Padding%2A>

6. Выберите элемент управления <xref:System.Windows.Forms.GroupBox> в элементе управления и переместите его в центр <xref:System.Windows.Forms.GroupBox>. <xref:System.Windows.Forms.Button>

   Линии привязки отображаются на большее расстояние от границ <xref:System.Windows.Forms.GroupBox> элемента управления. Это расстояние является суммой <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Margin%2A> свойстваэлемента<xref:System.Windows.Forms.GroupBox> управления и свойстваэлементауправления.<xref:System.Windows.Forms.Control.Padding%2A>

## <a name="size-controls-automatically"></a>Автоматическое изменение размера элементов управления

В некоторых приложениях размер элемента управления не будет одинаковым во время выполнения, так как он находился во время разработки. Текст <xref:System.Windows.Forms.Button> элемента управления, например, может быть взят из базы данных и его длина не известна заранее.

Если свойство имеет `true`значение, то размер элемента управления изменится на его содержимое. <xref:System.Windows.Forms.Control.AutoSize%2A> Дополнительные сведения см. в разделе [Общие сведения о свойстве AutoSize](autosize-property-overview.md).

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a>Размещение элементов управления в форме с помощью свойства AutoSize

1. Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в свою форму.

2. Измените значение <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.AutoSize%2A> свойства элемента управления на **true**.

3. <xref:System.Windows.Forms.Button> Измените свойство<xref:System.Windows.Forms.Control.Text%2A> элемента управления на **Эта кнопка имеет длинную строку для свойства Text**.

   При фиксации изменения <xref:System.Windows.Forms.Button> элемент управления изменяет свой размер в соответствии с новым текстом.

4. Перетащите другой <xref:System.Windows.Forms.Button> элемент управления из **панели элементов** в форму.

5. <xref:System.Windows.Forms.Button> Измените свойство<xref:System.Windows.Forms.Control.Text%2A> элемента управления на "**Эта кнопка содержит длинную строку для своего текстового свойства".**

   При фиксации изменения <xref:System.Windows.Forms.Button> размер элемента управления не изменяется, а текст обрезается по правому краю элемента управления.

6. <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Padding.All%2A>Измените свойство, развернув запись в окне "Свойства" и задав для свойства значение 5. <xref:System.Windows.Forms.Control.Padding%2A>

   Текст во внутренней части элемента управления обрезается по всем четырем сторонам.

7. Измените значение <xref:System.Windows.Forms.Control.AutoSize%2A> свойстваэлемента управления на true <xref:System.Windows.Forms.Button> .

   <xref:System.Windows.Forms.Button> Элемент управления изменяет свой размер, чтобы охватывать всю строку. Кроме того, заполнение вокруг текста было добавлено, что приводит <xref:System.Windows.Forms.Button> к раскрытию элемента управления во всех четырех направлениях.

8. Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в свою форму. Поместите его в правый нижний угол формы.

9. Измените значение <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.AutoSize%2A> свойства элемента управления на **true**.

10. Присвойте <xref:System.Windows.Forms.Control.Anchor%2A> <xref:System.Windows.Forms.AnchorStyles.Bottom> свойству<xref:System.Windows.Forms.AnchorStyles.Right>элемента управления значение,. <xref:System.Windows.Forms.Button>

11. <xref:System.Windows.Forms.Button> Измените свойство<xref:System.Windows.Forms.Control.Text%2A> элемента управления на "**Эта кнопка содержит длинную строку для своего текстового свойства".**

   При фиксации изменения <xref:System.Windows.Forms.Button> элемент управления изменяет свой размер в направлении влево. Как правило, автоматическое изменение размера приведет к увеличению размера элемента управления в направлении, противоположном его <xref:System.Windows.Forms.Control.Anchor%2A> значению свойства.

## <a name="autosize-and-autosizemode-properties"></a>Свойства AutoSize и AutoSizeMode

 Некоторые элементы управления поддерживают `AutoSizeMode` свойство, которое обеспечивает более детализированный контроль над автоматическим изменением размеров элемента управления.

### <a name="use-the-autosizemode-property"></a>Использование свойства AutoSizeMode

1. Перетащите элемент управления <xref:System.Windows.Forms.Panel> из **панели элементов** в свою форму.

2. Присвойте <xref:System.Windows.Forms.Panel> <xref:System.Windows.Forms.Control.AutoSize%2A> свойству элемента управления значение **true**.

3. Перетащите элемент управления из <xref:System.Windows.Forms.Panel> **панели элементов** в элемент управления. <xref:System.Windows.Forms.Button>

4. Разместите <xref:System.Windows.Forms.Panel> элемент управления в правом нижнем углу элемента управления. <xref:System.Windows.Forms.Button>

5. <xref:System.Windows.Forms.Panel> Выберите элемент управления и захватите правый нижний маркер изменения размера. Измените размер <xref:System.Windows.Forms.Panel> элемента управления, чтобы он был больше и меньше.

   > [!NOTE]
   > Можно свободно изменять размер <xref:System.Windows.Forms.Panel> элемента управления, но его нельзя уменьшить, чем расположение <xref:System.Windows.Forms.Button> нижнего правого угла элемента управления. Это поведение задается значением `AutoSizeMode` свойства по умолчанию, то есть. <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>

6. Присвойте <xref:System.Windows.Forms.Panel> `AutoSizeMode` свойству<xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>элемента управления значение.

   Размеры элемента управления заключаются в <xref:System.Windows.Forms.Button> элемент управления. <xref:System.Windows.Forms.Panel> Изменить размер <xref:System.Windows.Forms.Panel> элемента управления нельзя.

7. Перетащите элемент управления в левый верхний угол <xref:System.Windows.Forms.Panel> элемента управления. <xref:System.Windows.Forms.Button>

   Элемент управления изменяется <xref:System.Windows.Forms.Button> на новое расположение элемента управления. <xref:System.Windows.Forms.Panel>

## <a name="next-steps"></a>Следующие шаги

Существует множество других функций макета для упорядочения элементов управления в Windows Forms приложениях. Ниже приведены некоторые сочетания, которые можно использовать.

- Создание формы с помощью <xref:System.Windows.Forms.TableLayoutPanel> элемента управления. Дополнительные сведения см. [в разделе Пошаговое руководство. Упорядочивание элементов управления в Windows Forms с помощью](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)TableLayoutPanel. Попробуйте изменить значения <xref:System.Windows.Forms.TableLayoutPanel> <xref:System.Windows.Forms.Control.Padding%2A> свойства элемента управления <xref:System.Windows.Forms.Control.Margin%2A> , а также свойство для его дочерних элементов управления.

- Попробуйте тот же эксперимент с помощью <xref:System.Windows.Forms.FlowLayoutPanel> элемента управления. Дополнительные сведения см. [в разделе Пошаговое руководство. Упорядочивание элементов управления в Windows Forms с помощью](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)FlowLayoutPanel.

- Поэкспериментируйте с закреплением дочерних <xref:System.Windows.Forms.Panel> элементов управления в элементе управления. Свойство является более общим реализацией <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> свойства, и вы можете удовлетворить себе, что это так, поместив дочерний элемент управления в <xref:System.Windows.Forms.Panel> элемент управления и установив для <xref:System.Windows.Forms.Control.Dock%2A> свойства дочернего элемента управления значение <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.DockStyle.Fill>. Задайте для <xref:System.Windows.Forms.Control.Padding%2A> свойства элементауправленияразличныезначенияиобратитевниманиенарезультат.<xref:System.Windows.Forms.Panel>

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [Свойство AutoSize](autosize-property-overview.md)
- [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
