---
title: Размещение элементов управления с заполнением, полями и свойством AutoSize
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: ca7942c04434592f2541252c47ac3dd17e03dbac
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742374"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a>Пошаговое руководство. размещение элементов управления с заполнением, полями и свойством AutoSize

Точное расположение элементов управления на форме является важным для многих приложений. **Конструктор Windows Forms** в Visual Studio предоставляет множество инструментов макета для решения этой задачи. Три из наиболее важных: свойства <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>и <xref:System.Windows.Forms.Control.AutoSize%2A>, которые имеются во всех элементах управления Windows Forms.

Свойство <xref:System.Windows.Forms.Control.Margin%2A> определяет поле вокруг элемента управления, благодаря которому обеспечивается определенное расстояние между границами этого элемента и другими элементами.

Свойство <xref:System.Windows.Forms.Control.Padding%2A> определяет поле внутри элемента управления, благодаря которому обеспечивается определенное расстояние между содержимым элемента управления (например, значением свойства <xref:System.Windows.Forms.Control.Text%2A>) и его границами.

На рисунке ниже демонстрируется значение свойств <xref:System.Windows.Forms.Control.Padding%2A> и <xref:System.Windows.Forms.Control.Margin%2A> элемента управления.

![Поля и заполнение для элементов управления Windows Forms](./media/vs-winformpadmargin.gif)

Свойство <xref:System.Windows.Forms.Control.AutoSize%2A> указывает элементу управления на автоматическое изменение размера в соответствии с его содержимым. Размер не будет меньше, чем значение исходного свойства <xref:System.Windows.Forms.Control.Size%2A>, и оно будет учитывать значение его свойства <xref:System.Windows.Forms.Control.Padding%2A>.

## <a name="prerequisites"></a>предварительные требования

Для выполнения этого пошагового руководства потребуется Visual Studio.

## <a name="create-the-project"></a>Создание проекта

1. В Visual Studio создайте проект **приложения Windows** с именем `LayoutExample`.

2. Выберите форму в **конструктор Windows Forms**.

## <a name="set-margins-for-controls"></a>Установка полей для элементов управления

Расстояние по умолчанию между элементами управления можно задать с помощью свойства <xref:System.Windows.Forms.Control.Margin%2A>. При перемещении элемента управления, достаточно близкого к другому элементу управления, вы увидите линию привязки, показывающую поля для этих двух элементов управления. Перемещаемый элемент управления также будет привязан к расстоянию, заданному полями.

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a>Размещение элементов управления в форме с помощью свойства Margin

1. Перетащите два элемента управления <xref:System.Windows.Forms.Button> из **панели элементов** в форму.

2. Выберите один из элементов управления <xref:System.Windows.Forms.Button> и переместите его ближе к другому, пока они не будут почти соприкасаются.

   Обратите внимание на линию привязки, которая появляется между ними. Это расстояние является суммой значений двух элементов управления <xref:System.Windows.Forms.Control.Margin%2A>. Перемещаемый элемент управления привязывается к этому расстоянию. Дополнительные сведения см. [в разделе Пошаговое руководство. Упорядочивание элементов управления в Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).

3. Измените свойство <xref:System.Windows.Forms.Control.Margin%2A> одного из элементов управления, развернув запись <xref:System.Windows.Forms.Control.Margin%2A> в окне **Свойства** и установив для свойства <xref:System.Windows.Forms.Padding.All%2A> значение **20**.

4. Выберите один из элементов управления <xref:System.Windows.Forms.Button> и переместите его ближе к другому.

   Линия привязки, определяющая сумму значений полей, больше, и элемент управления привязывается к большему расстоянию от другого элемента управления.

5. Измените свойство <xref:System.Windows.Forms.Control.Margin%2A> выбранного элемента управления, развернув запись <xref:System.Windows.Forms.Control.Margin%2A> в окне **Свойства** и установив для свойства <xref:System.Windows.Forms.Padding.Top%2A> значение **5**.

6. Переместите выбранный элемент управления под другим элементом управления и обратите внимание, что линия привязки короче. Переместите выбранный элемент управления влево от другого элемента управления и обратите внимание, что линия привязки содержит значение, наблюдаемое на шаге 4.

7. Можно задать для каждого из аспектов свойства <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, различные значения, или же можно задать для них одно и то же значение с помощью свойства <xref:System.Windows.Forms.Padding.All%2A>.

## <a name="set-padding-for-controls"></a>Задание заполнения для элементов управления

Чтобы обеспечить точный макет, необходимый для вашего приложения, элементы управления часто будут содержать дочерние элементы управления. Если необходимо указать границу границы дочернего элемента управления для границы родительского элемента управления, используйте свойство <xref:System.Windows.Forms.Control.Padding%2A> родительского элемента в сочетании со свойством <xref:System.Windows.Forms.Control.Margin%2A> дочернего элемента управления. Свойство <xref:System.Windows.Forms.Control.Padding%2A> также используется для управления сходством содержимого элемента управления (например, свойства <xref:System.Windows.Forms.Control.Text%2A> <xref:System.Windows.Forms.Button> элемента управления) с его границами.

### <a name="arrange-controls-on-your-form-using-padding"></a>Размещение элементов управления в форме с помощью заполнения

1. Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в свою форму.

2. Измените значение свойства <xref:System.Windows.Forms.Control.AutoSize%2A> элемента управления <xref:System.Windows.Forms.Button> на **true**.

3. Измените свойство <xref:System.Windows.Forms.Control.Padding%2A>, развернув запись <xref:System.Windows.Forms.Control.Padding%2A> в окне **Свойства** и установив для свойства <xref:System.Windows.Forms.Padding.All%2A> значение **5**.

   Элемент управления расширяется, чтобы предоставить место для нового заполнения.

4. Перетащите элемент управления <xref:System.Windows.Forms.GroupBox> из **панели элементов** в свою форму. Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в элемент управления <xref:System.Windows.Forms.GroupBox>. Поместите элемент управления <xref:System.Windows.Forms.Button>, чтобы он был сброшен в правый нижний угол элемента управления <xref:System.Windows.Forms.GroupBox>.

   Обратите внимание на линии привязки, которые отображаются, так как элемент управления <xref:System.Windows.Forms.Button> приближает нижнюю и правую границы элемента управления <xref:System.Windows.Forms.GroupBox>. Эти линии привязки соответствуют свойству <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Button>.

5. Измените свойство <xref:System.Windows.Forms.Control.Padding%2A> элемента управления <xref:System.Windows.Forms.GroupBox>, развернув запись <xref:System.Windows.Forms.Control.Padding%2A> в окне **Свойства** и установив для свойства <xref:System.Windows.Forms.Padding.All%2A> значение **20**.

6. Выберите элемент управления <xref:System.Windows.Forms.Button> в элементе управления <xref:System.Windows.Forms.GroupBox> и переместите его в центр <xref:System.Windows.Forms.GroupBox>.

   Линии привязки отображаются на большее расстояние от границ элемента управления <xref:System.Windows.Forms.GroupBox>. Это расстояние является суммой свойства <xref:System.Windows.Forms.Control.Margin%2A> элемента управления <xref:System.Windows.Forms.Button> и свойства <xref:System.Windows.Forms.Control.Padding%2A> элемента управления <xref:System.Windows.Forms.GroupBox>.

## <a name="size-controls-automatically"></a>Автоматическое изменение размера элементов управления

В некоторых приложениях размер элемента управления не будет одинаковым во время выполнения, так как он находился во время разработки. Текст элемента управления <xref:System.Windows.Forms.Button>, например, может быть взят из базы данных и его длина не известна заранее.

Если свойство <xref:System.Windows.Forms.Control.AutoSize%2A> имеет значение `true`, размер элемента управления будет таким же, как и его содержимое. Дополнительные сведения см. в разделе [Общие сведения о свойстве AutoSize](autosize-property-overview.md).

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a>Размещение элементов управления в форме с помощью свойства AutoSize

1. Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в свою форму.

2. Измените значение свойства <xref:System.Windows.Forms.Control.AutoSize%2A> элемента управления <xref:System.Windows.Forms.Button> на **true**.

3. Измените свойство <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.Button> на эту кнопку, чтобы оно **было длинной строкой для свойства Text**.

   При фиксации изменения размер элемента управления <xref:System.Windows.Forms.Button> изменяется в соответствии с новым текстом.

4. Перетащите еще один элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в форму.

5. Измените свойство <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.Button> на "**Эта кнопка содержит длинную строку для своего свойства текста".**

   При фиксации изменения размер элемента управления <xref:System.Windows.Forms.Button> не изменяется, а текст обрезается по правому краю элемента управления.

6. Измените свойство <xref:System.Windows.Forms.Control.Padding%2A>, развернув запись <xref:System.Windows.Forms.Control.Padding%2A> в окне **Свойства** и установив для свойства <xref:System.Windows.Forms.Padding.All%2A> значение **5**.

   Текст во внутренней части элемента управления обрезается по всем четырем сторонам.

7. Измените свойство <xref:System.Windows.Forms.Control.AutoSize%2A> элемента управления <xref:System.Windows.Forms.Button> на **true**.

   Элемент управления <xref:System.Windows.Forms.Button> изменяет свой размер, чтобы охватывать всю строку. Кроме того, вокруг текста добавляется заполнение, в результате чего элемент управления <xref:System.Windows.Forms.Button> разворачивается во всех четырех направлениях.

8. Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в свою форму. Поместите его в правый нижний угол формы.

9. Измените значение свойства <xref:System.Windows.Forms.Control.AutoSize%2A> элемента управления <xref:System.Windows.Forms.Button> на **true**.

10. Задайте для свойства <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> значение <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.

11. Измените свойство <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.Button> на "**Эта кнопка содержит длинную строку для своего свойства текста".**

   При фиксации изменения размер элемента управления <xref:System.Windows.Forms.Button> изменяется в направлении влево. Как правило, автоматическое изменение размера приведет к увеличению размера элемента управления в направлении, противоположном значению свойства <xref:System.Windows.Forms.Control.Anchor%2A>.

## <a name="autosize-and-autosizemode-properties"></a>Свойства AutoSize и AutoSizeMode

 Некоторые элементы управления поддерживают свойство `AutoSizeMode`, которое обеспечивает более детализированный контроль над автоматическим изменением размеров элемента управления.

### <a name="use-the-autosizemode-property"></a>Использование свойства AutoSizeMode

1. Перетащите элемент управления <xref:System.Windows.Forms.Panel> из **панели элементов** в свою форму.

2. Присвойте свойству <xref:System.Windows.Forms.Control.AutoSize%2A> <xref:System.Windows.Forms.Panel> элемента управления значение **true**.

3. Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в элемент управления <xref:System.Windows.Forms.Panel>.

4. Поместите элемент управления <xref:System.Windows.Forms.Button> в правый нижний угол элемента управления <xref:System.Windows.Forms.Panel>.

5. Выберите элемент управления <xref:System.Windows.Forms.Panel> и захватите правый нижний маркер изменения размера. Измените размер элемента управления <xref:System.Windows.Forms.Panel>, чтобы он был больше и меньше.

   > [!NOTE]
   > Можно свободно изменить размер элемента управления <xref:System.Windows.Forms.Panel>, но его размер меньше, чем расположение нижнего правого угла элемента управления <xref:System.Windows.Forms.Button>. Это поведение задается значением по умолчанию свойства `AutoSizeMode`, которое <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.

6. Установите для свойства `AutoSizeMode` элемента управления <xref:System.Windows.Forms.Panel> значение <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.

   Размеры элемента управления <xref:System.Windows.Forms.Panel>, чтобы заключить <xref:System.Windows.Forms.Button> элемент управления. Изменить размер элемента управления <xref:System.Windows.Forms.Panel> нельзя.

7. Перетащите элемент управления <xref:System.Windows.Forms.Button> в левый верхний угол элемента управления <xref:System.Windows.Forms.Panel>.

   <xref:System.Windows.Forms.Panel> элемент управления изменяется на новое расположение элемента управления <xref:System.Windows.Forms.Button>.

## <a name="next-steps"></a>Дальнейшие действия

Существует множество других функций макета для упорядочения элементов управления в Windows Forms приложениях. Ниже приведены некоторые сочетания, которые можно использовать.

- Создание формы с помощью элемента управления <xref:System.Windows.Forms.TableLayoutPanel>. Дополнительные сведения см. [в разделе Пошаговое руководство. Упорядочивание элементов управления в Windows Forms с помощью TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md). Попробуйте изменить значения свойства <xref:System.Windows.Forms.Control.Padding%2A> элемента управления <xref:System.Windows.Forms.TableLayoutPanel>, а также свойства <xref:System.Windows.Forms.Control.Margin%2A> дочерних элементов управления.

- Попробуйте тот же эксперимент, используя элемент управления <xref:System.Windows.Forms.FlowLayoutPanel>. Дополнительные сведения см. [в разделе Пошаговое руководство. Упорядочивание элементов управления в Windows Forms с помощью элемента FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).

- Поэкспериментируйте с закреплением дочерних элементов управления в элементе управления <xref:System.Windows.Forms.Panel>. Свойство <xref:System.Windows.Forms.Control.Padding%2A> является более общим реализацией свойства <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>, и вы можете удовлетворить, что это так, поместив дочерний элемент управления в элемент управления <xref:System.Windows.Forms.Panel> и установив для свойства <xref:System.Windows.Forms.Control.Dock%2A> дочернего элемента управления значение <xref:System.Windows.Forms.DockStyle.Fill>. Задайте для свойства <xref:System.Windows.Forms.Control.Padding%2A> элемента управления <xref:System.Windows.Forms.Panel> различные значения и обратите внимание на результат.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [Свойство AutoSize](autosize-property-overview.md)
- [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
