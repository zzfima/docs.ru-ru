---
title: Упорядочение элементов управления с помощью TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: 803a56f6416cf3b718890e96cf9f36ae6c4ee471
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740316"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel

В некоторых приложениях требуется форма, макет которой изменяется надлежащим образом при изменении размера формы или содержимого. Если необходим динамический макет и вы не хотите обрабатывать события <xref:System.Windows.Forms.Control.Layout> явно в коде, рассмотрите возможность использования панели макета.

Элементы управления <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel> предоставляют удобные способы упорядочения элементов управления в форме. Они обеспечивают автоматическую настраиваемую возможность управления относительным положением содержащихся в них дочерних элементов управления и предоставляют функции динамического макета во время выполнения и таким образом могут изменять размер и положение дочерних элементов управления по мере измерения размеров родительской формы. Панели макета могут быть вложенными в других панелях макета, что позволяет реализовывать сложные пользовательские интерфейсы.

Элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает свое содержимое в определенном направлении, горизонтальном или вертикальном. Его содержимое может быть перенесено из одной строки в следующую или из одного столбца в следующий. Кроме того, вместо переноса содержимое может обрезаться. Дополнительные сведения см. [в разделе Пошаговое руководство. Упорядочивание элементов управления в Windows Forms с помощью элемента FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).

<xref:System.Windows.Forms.TableLayoutPanel> упорядочивает свое содержимое в сетке, предоставляя функциональные возможности, аналогичные элементу HTML \<TABLE >. Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> позволяет размещать элементы управления в макете сетки, не требуя точного указания положения каждого отдельного элемента управления. Его ячейки организованы в строки и столбцы, и они могут быть разного размера. Ячейки можно объединять между строками и столбцами. Ячейки могут содержать все, что может содержать форма, и вести себя в других отношениях в качестве контейнеров.

Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> также предоставляет возможность пропорционального изменения размера во время выполнения, поэтому макет может плавно меняться по мере изменения размера формы. Это делает элемент управления <xref:System.Windows.Forms.TableLayoutPanel> хорошо подходящим для таких целей, как формы ввода данных и локализованные приложения. Дополнительные сведения см. в разделе [Пошаговое руководство. Создание формы Windows с изменяемым размером для ввода данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)) и [Пошаговое руководство. Создание локализуемых форм Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).

В общем случае не следует использовать элемент управления <xref:System.Windows.Forms.TableLayoutPanel> в качестве контейнера для всего макета. Используйте элементы управления <xref:System.Windows.Forms.TableLayoutPanel>, чтобы обеспечить пропорциональные возможности изменения размера для частей макета.

В данном пошаговом руководстве представлены следующие задачи.

- Создание проекта Windows Forms

- Упорядочение элементов управления в строках и столбцах

- Установка свойств строк и столбцов

- Объединение строк и столбцов с помощью элемента управления

- Автоматическая обработка перегрузок

- Вставка элементов управления двойным щелчком по ним в панели элементов

- Вставка элемента управления путем рисования его контура

- Переназначение существующих элементов управления другим родительским элементам

После завершения вы будете понимать роль, которую играют эти важные функции макета.

## <a name="creating-the-project"></a>Создание проекта

Первым шагом является создание проекта и настройка формы.

#### <a name="to-create-the-project"></a>Создание проекта

1. Создайте проект приложения Windows с именем "Таблелайаутпанелексампле". Дополнительные сведения см. [в разделе инструкции. Создание проекта Windows Forms приложения](/visualstudio/ide/step-1-create-a-windows-forms-application-project) .

2. Выберите форму в конструкторе **Windows** **Forms**.

## <a name="arranging-controls-in-rows-and-columns"></a>Упорядочение элементов управления в строках и столбцах

Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> позволяет легко упорядочивать элементы управления по строкам и столбцам.

#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>Размещение элементов управления в строках и столбцах с помощью TableLayoutPanel

1. Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму. Обратите внимание, что по умолчанию элемент управления <xref:System.Windows.Forms.TableLayoutPanel> содержит четыре ячейки.

2. Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в элемент управления <xref:System.Windows.Forms.TableLayoutPanel> и поместите его в одну из ячеек. Обратите внимание, что элемент управления <xref:System.Windows.Forms.Button> создается в выбранной ячейке.

3. Перетащите еще три <xref:System.Windows.Forms.Button> элементы управления из **панели элементов** в элемент управления <xref:System.Windows.Forms.TableLayoutPanel>, чтобы каждая ячейка содержала кнопку.

4. Возьмите вертикальный маркер изменения размера между двумя столбцами и переместите его влево. Обратите внимание, что размеры элементов управления <xref:System.Windows.Forms.Button> в первом столбце изменяются до меньшей ширины, а размер элементов управления <xref:System.Windows.Forms.Button> во втором столбце не изменяется.

5. Возьмите вертикальный маркер изменения размера между двумя столбцами и переместите его вправо. Обратите внимание, что <xref:System.Windows.Forms.Button> элементы управления в первом столбце возвращают исходный размер, а элементы управления <xref:System.Windows.Forms.Button> во втором столбце перемещаются вправо.

6. Переместите горизонтальный маркер изменения размера вверх и вниз, чтобы увидеть воздействие на элементы управления на панели.

## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>Размещение элементов управления внутри ячеек с помощью закрепления и привязки

Поведение привязки дочерних элементов управления в <xref:System.Windows.Forms.TableLayoutPanel> отличается от поведения в других контейнерных элементах управления. Поведение закрепления дочерних элементов управления аналогично поведению других элементов управления контейнера.

#### <a name="positioning-controls-within-cells"></a>Размещение элементов управления внутри ячеек

1. Выберите первый элемент управления <xref:System.Windows.Forms.Button>. Измените значение его свойства <xref:System.Windows.Forms.Control.Dock%2A> на <xref:System.Windows.Forms.DockStyle.Fill>. Обратите внимание, что элемент управления <xref:System.Windows.Forms.Button> расширяется для заполнения ячейки.

2. Выберите один из других элементов управления <xref:System.Windows.Forms.Button>. Измените значение его свойства <xref:System.Windows.Forms.Control.Anchor%2A> на <xref:System.Windows.Forms.AnchorStyles.Right>. Обратите внимание, что она перемещается таким образом, что правая граница находится ближе к правой границе ячейки. Расстояние между границами является суммой свойства <xref:System.Windows.Forms.Control.Margin%2A> элемента управления <xref:System.Windows.Forms.Button> и свойства <xref:System.Windows.Forms.Control.Padding%2A> панели.

3. Измените значение свойства <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> на <xref:System.Windows.Forms.AnchorStyles.Right> и <xref:System.Windows.Forms.AnchorStyles.Left>. Обратите внимание, что размер элемента управления изменяется по ширине ячейки, при этом учитывается значение <xref:System.Windows.Forms.Control.Margin%2A> и <xref:System.Windows.Forms.Control.Padding%2A>.

4. Повторите шаги 2 и 3 с помощью стилей <xref:System.Windows.Forms.AnchorStyles.Top> и <xref:System.Windows.Forms.AnchorStyles.Bottom>.

## <a name="setting-row-and-column-properties"></a>Установка свойств строк и столбцов

Можно задать отдельные свойства строк и столбцов с помощью коллекций <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> и <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>.

#### <a name="to-set-row-and-column-properties"></a>Задание свойств строк и столбцов

1. Выберите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> в **конструктор Windows Forms**.

2. В окнах **свойств** откройте коллекцию <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>, нажав кнопку с многоточием (![кнопку с многоточием (...) в окно свойств кнопки Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом с записью **Columns** .

3. Выберите первый столбец и измените значение его свойства <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> на <xref:System.Windows.Forms.SizeType.AutoSize>. Нажмите кнопку **ОК** , чтобы принять изменения. Обратите внимание, что ширина первого столбца уменьшается в соответствии с элементом управления <xref:System.Windows.Forms.Button>. Также обратите внимание, что ширина столбца не может изменяться.

4. В окне **Свойства** откройте коллекцию <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> и выберите первый столбец. Измените значение его свойства <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> на <xref:System.Windows.Forms.SizeType.Percent>. Нажмите кнопку **ОК** , чтобы принять изменения. Измените ширину элемента управления <xref:System.Windows.Forms.TableLayoutPanel> до большей ширины и обратите внимание, что ширина первого столбца расширяется. Измените ширину элемента управления <xref:System.Windows.Forms.TableLayoutPanel> до меньшей ширины и обратите внимание, что кнопки в первом столбце имеют размер в соответствии с ячейкой. Также обратите внимание, что размер столбца можно изменять.

5. В окне **Свойства** откройте коллекцию <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> и выберите все перечисленные столбцы. Задайте для каждого свойства <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> значение <xref:System.Windows.Forms.SizeType.Percent>. Нажмите кнопку **ОК** , чтобы принять изменения. Повторите операцию с коллекцией <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A>.

6. Извлеките один из угловых маркеров изменения размера и измените ширину и высоту элемента управления <xref:System.Windows.Forms.TableLayoutPanel>. Обратите внимание, что размер строк и столбцов изменяется по мере изменения размера элемента управления <xref:System.Windows.Forms.TableLayoutPanel>. Также обратите внимание, что размер строк и столбцов можно изменять с помощью маркеров горизонтального и вертикального размера.

## <a name="spanning-rows-and-columns-with-a-control"></a>Объединение строк и столбцов с помощью элемента управления

Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> добавляет несколько новых свойств в элементы управления во время разработки. Два из этих свойств `RowSpan` и `ColumnSpan`. Эти свойства можно использовать, чтобы сделать элемент управления более чем одной строкой или столбцом.

#### <a name="to-span-rows-and-columns-with-a-control"></a>Объединение строк и столбцов с помощью элемента управления

1. Выберите элемент управления <xref:System.Windows.Forms.Button> в первой строке и первом столбце.

2. В окнах **свойств** измените значение свойства `ColumnSpan` на **2**. Обратите внимание, что элемент управления <xref:System.Windows.Forms.Button> заполняет первый столбец и второй столбец. Кроме того, обратите внимание, что для удовлетворения этого изменения была добавлена дополнительная строка.

3. Повторите шаг 2 для свойства `RowSpan`.

## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Вставка элементов управления двойным щелчком по ним в панели элементов

Вы можете заполнять свой элемент управления <xref:System.Windows.Forms.TableLayoutPanel> , дважды щелкая элементы управления в **панели элементов**.

#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>Вставка элементов управления двойным щелчком по ним в панели элементов

1. Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.

2. Дважды щелкните значок элемента управления <xref:System.Windows.Forms.Button> в **панели элементов**. Обратите внимание, что в первой ячейке элемента управления <xref:System.Windows.Forms.TableLayoutPanel> появляется новый элемент управления "Кнопка".

3. Дважды щелкните несколько других элементов управления в **панели элементов**. Обратите внимание, что новые элементы управления последовательно появляются в незанятых ячейках элемента управления <xref:System.Windows.Forms.TableLayoutPanel>. Также обратите внимание, что элемент управления <xref:System.Windows.Forms.TableLayoutPanel> расширяется для размещения новых элементов управления, если открытые ячейки недоступны.

## <a name="automatic-handling-of-overflows"></a>Автоматическая обработка перегрузок

При вставке элементов управления в элемент управления <xref:System.Windows.Forms.TableLayoutPanel> для новых элементов управления могут выпустить пустые ячейки. Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> обрабатывает эту ситуацию автоматически, увеличивая число ячеек.

#### <a name="to-observe-automatic-handling-of-overflows"></a>Наблюдение за автоматической обработкой перегрузок

1. Если в элементе управления <xref:System.Windows.Forms.TableLayoutPanel> по-прежнему есть пустые ячейки, продолжайте вставлять новые элементы управления <xref:System.Windows.Forms.Button>, пока элемент управления <xref:System.Windows.Forms.TableLayoutPanel> не будет заполнен.

2. После заполнения элемента управления <xref:System.Windows.Forms.TableLayoutPanel> дважды щелкните значок <xref:System.Windows.Forms.Button> на **панели элементов** , чтобы вставить другой элемент управления <xref:System.Windows.Forms.Button>. Обратите внимание, что элемент управления <xref:System.Windows.Forms.TableLayoutPanel> создает новые ячейки для размещения нового элемента управления. Вставьте еще несколько элементов управления и обратите внимание на поведение изменения размера.

3. Измените значение свойства <xref:System.Windows.Forms.TableLayoutPanel> элемента управления <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> на <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>. Дважды щелкните значок <xref:System.Windows.Forms.Button> на **панели элементов** , чтобы вставить элементы управления <xref:System.Windows.Forms.Button>, пока не будет заполнен элемент управления <xref:System.Windows.Forms.TableLayoutPanel>. Дважды щелкните значок <xref:System.Windows.Forms.Button> на **панели элементов** . Обратите внимание, что в **конструктор Windows Forms** появляется сообщение об ошибке, информирующее о невозможности создания дополнительных строк и столбцов.

## <a name="inserting-a-control-by-drawing-its-outline"></a>Вставка элемента управления путем рисования его контура

Вы можете вставить элемент управления в элемент управления <xref:System.Windows.Forms.TableLayoutPanel> и задать его размер, нарисовав его контур в ячейке.

#### <a name="to-insert-a-control-by-drawing-its-outline"></a>Вставка элемента управления путем рисования его контура

1. Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.

2. В **панели элементов**щелкните значок элемента управления <xref:System.Windows.Forms.Button> . Не перетаскивайте его в форму.

3. Наведите указатель мыши на элемент управления <xref:System.Windows.Forms.TableLayoutPanel> . Обратите внимание, что указатель превратился в перекрестие с прикрепленным значком элемента управления <xref:System.Windows.Forms.Button> .

4. Нажмите и удерживайте кнопку мыши.

5. Перемещайте указатель мыши, чтобы нарисовать контур элемента управления <xref:System.Windows.Forms.Button> . Когда вас устроит размер, отпустите кнопку мыши. Обратите внимание, что элемент управления <xref:System.Windows.Forms.Button> создается в ячейке, в которой был нарисован контур элемента управления.

## <a name="multiple-controls-within-cells-are-not-permitted"></a>Использование нескольких элементов управления в ячейках не допускается

Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> может содержать только один дочерний элемент управления на одну ячейку.

#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>Демонстрация того, что несколько элементов управления в ячейках не разрешены

- Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в элемент управления <xref:System.Windows.Forms.TableLayoutPanel> и поместите его в одну из занятых ячеек. Обратите внимание, что элемент управления <xref:System.Windows.Forms.TableLayoutPanel> не позволяет удалить элемент управления <xref:System.Windows.Forms.Button> в занятую ячейку.

## <a name="swapping-controls"></a>Переключение элементов управления

Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> позволяет менять местами элементы управления, занимающие две разные ячейки.

#### <a name="to-swap-controls"></a>Переключение элементов управления

- Перетащите один из <xref:System.Windows.Forms.Button> элементов управления из занятой ячейки и поместите в другую занятую ячейку. Обратите внимание, что два элемента управления перемещаются из одной ячейки в другую.

## <a name="next-steps"></a>Дальнейшие действия

Используя сочетание панелей макета и элементов управления, можно создавать сложные макеты. Рекомендуется также дополнительно исследовать следующие моменты.

- Попробуйте изменить размер одного из элементов управления <xref:System.Windows.Forms.Button> до большего размера и обратите внимание на изменение макета.

- Вставьте фрагменты нескольких элементов управления в элемент управления <xref:System.Windows.Forms.TableLayoutPanel> и обратите внимание на то, как вставляются элементы управления.

- Панели макета могут содержать другие панели макета. Попробуйте вставить элемент управления <xref:System.Windows.Forms.TableLayoutPanel> в существующий элемент управления.

- Закрепите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> в родительской форме. Измените размер этой формы и обратите внимание, как это отражается на макете.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Пошаговое руководство. Создание в Windows Forms формы для ввода данных переменного размера](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))
- [Пошаговое руководство. Создание локализуемых форм Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))
- [Советы по использованию элемента управления TableLayoutPanel](best-practices-for-the-tablelayoutpanel-control.md)
- [Свойство AutoSize](autosize-property-overview.md)
- [Практическое руководство. Закрепление элементов управления в формах Windows Forms](how-to-dock-controls-on-windows-forms.md)
- [Практическое руководство. Привязка элементов управления в формах Windows Forms](how-to-anchor-controls-on-windows-forms.md)
- [Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств Padding, Margins и AutoSize](windows-forms-controls-padding-autosize.md)
