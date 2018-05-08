---
title: Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: 6b98495fb967b7f3b5885f940c348b5cba33cb18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel
В некоторых приложениях требуется форма, макет которой изменяется надлежащим образом при изменении размера формы или содержимого. Если необходим динамический макет и вы не хотите обрабатывать события <xref:System.Windows.Forms.Control.Layout> явно в коде, рассмотрите возможность использования панели макета.  
  
 Элементы управления <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel> предоставляют удобные способы упорядочения элементов управления в форме. Они обеспечивают автоматическую настраиваемую возможность управления относительным положением содержащихся в них дочерних элементов управления и предоставляют функции динамического макета во время выполнения и таким образом могут изменять размер и положение дочерних элементов управления по мере измерения размеров родительской формы. Панели макета могут быть вложенными в других панелях макета, что позволяет реализовывать сложные пользовательские интерфейсы.  
  
 Элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает свое содержимое в определенном направлении, горизонтальном или вертикальном. Его содержимое может быть перенесено из одной строки в следующую или из одного столбца в следующий. Кроме того, вместо переноса содержимое может обрезаться. Дополнительные сведения см. в разделе [Пошаговое руководство: упорядочение элементов управления в Windows Forms с помощью элемента FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
 <xref:System.Windows.Forms.TableLayoutPanel> Упорядочивает содержимое в сетке, обеспечивая функциональные возможности, аналогичные HTML \<таблицы > элемент. <xref:System.Windows.Forms.TableLayoutPanel> Позволяет размещать элементы управления в виде сетки без необходимости точного указания положения каждого отдельного элемента управления. Его ячейки организованы в строки и столбцы, и они могут быть разного размера. Ячейки могут быть объединены между строками и столбцами. Ячейки могут содержать ничего формы может содержать и ведут себя во многих отношениях как контейнеры.  
  
 <xref:System.Windows.Forms.TableLayoutPanel> Управления также предоставляет возможность пропорционального изменения размера во время выполнения, то настройки макета можно плавно изменения размеров формы. Это делает <xref:System.Windows.Forms.TableLayoutPanel> управления хорошо подходит для форм ввода данных и локализованных приложений. Дополнительные сведения см. в разделе [Пошаговое руководство: создание Windows Forms формы для ввода данных](http://msdn.microsoft.com/library/e193b4fc-912a-4917-b036-b76c7a6f58ab) и [Пошаговое руководство: создание локализуемой формы Windows Forms](http://msdn.microsoft.com/library/c5240b6e-aaca-4286-9bae-778a416edb9c).  
  
 В общем случае не следует использовать <xref:System.Windows.Forms.TableLayoutPanel> управления как контейнер для всего макета. Используйте <xref:System.Windows.Forms.TableLayoutPanel> элементы управления для предоставления возможностей пропорционального изменения размера частей макета.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Создание проекта Windows Forms  
  
-   Упорядочение элементов управления в строках и столбцах  
  
-   Параметр строки и свойств столбца  
  
-   Объединение строк и столбцов с помощью элемента управления  
  
-   Автоматическая обработка переполнений  
  
-   Вставка элементов управления двойным щелчком по ним в панели элементов  
  
-   Вставка элемента управления путем рисования его контура  
  
-   Переназначение существующих элементов управления другим родительским элементам  
  
 После завершения вы будете понимать роль, которую играют эти важные функции макета.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Создание проекта  
 Первым шагом является создание проекта и настройка формы.  
  
#### <a name="to-create-the-project"></a>Создание проекта  
  
1.  Создайте проект приложения Windows, называется «TableLayoutPanelExample». Дополнительные сведения см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) .  
  
2.  Выберите форму в **Windows** **конструктор форм**.  
  
## <a name="arranging-controls-in-rows-and-columns"></a>Упорядочение элементов управления в строках и столбцах  
 <xref:System.Windows.Forms.TableLayoutPanel> Позволяет легко расположить элементы управления по строкам и столбцам.  
  
#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>Размещение элементов управления в строки и столбцы с помощью элемента TableLayoutPanel  
  
1.  Перетащите <xref:System.Windows.Forms.TableLayoutPanel> управления из **элементов** на форму. Обратите внимание, что по умолчанию <xref:System.Windows.Forms.TableLayoutPanel> элемент управления имеет четыре ячейки.  
  
2.  Перетащите <xref:System.Windows.Forms.Button> управления из **элементов** в <xref:System.Windows.Forms.TableLayoutPanel> управления и вставьте его в одну из ячеек. Обратите внимание, что <xref:System.Windows.Forms.Button> элемент управления создается внутри выделенная ячейка.  
  
3.  Перетащите еще три <xref:System.Windows.Forms.Button> управляет из **элементов** в <xref:System.Windows.Forms.TableLayoutPanel> таким образом, чтобы каждая ячейка содержит кнопки.  
  
4.  Захватите вертикальный маркер изменения размера между двумя столбцами и переместите его влево. Обратите внимание, что <xref:System.Windows.Forms.Button> элементов управления в первом столбце изменяются уменьшите ширину при размер <xref:System.Windows.Forms.Button> элементов управления во втором столбце не изменяется.  
  
5.  Захватите вертикальный маркер изменения размера между двумя столбцами и переместите его вправо. Обратите внимание, что <xref:System.Windows.Forms.Button> элементы управления в первом столбце, возвращают до исходного размера, а <xref:System.Windows.Forms.Button> элементов управления во втором столбце, перемещаются вправо.  
  
6.  Переместите горизонтальный маркер вверх и вниз, чтобы увидеть эффект в элементах управления в панели.  
  
## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>Размещение элементов управления внутри ячеек с использованием закрепления и привязки  
 Функции привязки дочерних элементов управления в <xref:System.Windows.Forms.TableLayoutPanel> отличается от поведения других контейнерных элементов управления. Закрепление дочерних элементов является таким же, как в других контейнерных элементов управления.  
  
#### <a name="positioning-controls-within-cells"></a>Размещение элементов управления внутри ячеек  
  
1.  Выберите первую <xref:System.Windows.Forms.Button> элемента управления. Измените значение его свойства <xref:System.Windows.Forms.Control.Dock%2A> на <xref:System.Windows.Forms.DockStyle.Fill>. Обратите внимание, что <xref:System.Windows.Forms.Button> элемент управления расширяется заполняет ячейку.  
  
2.  Выберите один из других <xref:System.Windows.Forms.Button> элементов управления. Измените значение его свойства <xref:System.Windows.Forms.Control.Anchor%2A> на <xref:System.Windows.Forms.AnchorStyles.Right>. Обратите внимание, что он перемещается так, чтобы его правая граница рядом с правой границей ячейки. Расстояние между границами равно сумме <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Margin%2A> свойство и панели <xref:System.Windows.Forms.Control.Padding%2A> свойство.  
  
3.  Измените значение <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> свойства <xref:System.Windows.Forms.AnchorStyles.Right> и <xref:System.Windows.Forms.AnchorStyles.Left>. Обратите внимание, что размер элемента управления по ширине ячейки с <xref:System.Windows.Forms.Control.Margin%2A> и <xref:System.Windows.Forms.Control.Padding%2A> принимать в расчет значения.  
  
4.  Повторите шаги 2 и 3 с <xref:System.Windows.Forms.AnchorStyles.Top> и <xref:System.Windows.Forms.AnchorStyles.Bottom> стили.  
  
## <a name="setting-row-and-column-properties"></a>Параметр строки и свойств столбца  
 Можно задать отдельные свойства строк и столбцов с помощью <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> и <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> коллекции.  
  
#### <a name="to-set-row-and-column-properties"></a>Чтобы задать свойства строк и столбцов  
  
1.  Выберите <xref:System.Windows.Forms.TableLayoutPanel> управления **конструктор Windows Forms**.  
  
2.  В **свойства** открытых окон <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> коллекции, нажав кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) кнопки рядом с **столбцы** входа.  
  
3.  Выберите первый столбец и измените значение его <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> свойства <xref:System.Windows.Forms.SizeType.AutoSize>. Нажмите кнопку **ОК** для внесения изменения. Обратите внимание, что ширина первого столбца меняется для соответствия <xref:System.Windows.Forms.Button> элемента управления. Также Обратите внимание, что ширину столбца, размеры которого не изменяются.  
  
4.  В **свойства** откройте <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> сбора и выберите первый столбец. Измените значение его <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> свойства <xref:System.Windows.Forms.SizeType.Percent>. Нажмите кнопку **ОК** для внесения изменения. Изменить размер <xref:System.Windows.Forms.TableLayoutPanel> управления на увеличение ширины и обратите внимание на то, ширина первого столбца при развертывании. Изменить размер <xref:System.Windows.Forms.TableLayoutPanel> управления уменьшите ширину и обратите внимание, что кнопки в первом столбце подгоняются под ячейки. Также Обратите внимание, что ширина столбца с раскрывающимися списками.  
  
5.  В **свойства** откройте <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> сбора и выберите все перечисленные столбцы. Установите для параметра каждый <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> свойства <xref:System.Windows.Forms.SizeType.Percent>. Нажмите кнопку **ОК** для внесения изменения. Повторите процедуру, используя <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> коллекции.  
  
6.  Потяните за один из маркеров изменения размера угла и изменить ширину и высоту <xref:System.Windows.Forms.TableLayoutPanel> элемента управления. Обратите внимание, что строки и столбцы изменяются как <xref:System.Windows.Forms.TableLayoutPanel> изменения размера элемента управления. Также Обратите внимание, что строки и столбцы, изменяемые с горизонтальной и вертикальной маркеры изменения размера.  
  
## <a name="spanning-rows-and-columns-with-a-control"></a>Объединение строк и столбцов с помощью элемента управления  
 <xref:System.Windows.Forms.TableLayoutPanel> Управления добавляет несколько новых свойств для элементов управления во время разработки. Два из этих свойств являются `RowSpan` и `ColumnSpan`. Эти свойства можно использовать, чтобы сделать элемент управления диапазона больше, чем одну строку или столбец.  
  
#### <a name="to-span-rows-and-columns-with-a-control"></a>Чтобы объединить строки и столбцы с помощью элемента управления  
  
1.  Выберите <xref:System.Windows.Forms.Button> элемента управления в первой строке и первом столбце.  
  
2.  В **свойства** windows, измените значение `ColumnSpan` свойства **2**. Обратите внимание, что <xref:System.Windows.Forms.Button> управления заполняет первый столбец, а во втором столбце. Также Обратите внимание, для реализации этого изменения будет добавлен появляется дополнительная строка.  
  
3.  Повторите шаг 2 для `RowSpan` свойства.  
  
## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>Вставка элементов управления двойным щелчком по ним в панели элементов  
 Можно заполнить вашей <xref:System.Windows.Forms.TableLayoutPanel> управления, дважды щелкните элементы управления в **элементов**.  
  
#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>Вставка элементов управления двойным щелчком по ним в панели элементов  
  
1.  Перетащите <xref:System.Windows.Forms.TableLayoutPanel> управления из **элементов** на форму.  
  
2.  Дважды щелкните значок элемента управления <xref:System.Windows.Forms.Button> в **панели элементов**. Обратите внимание, что отображается новый элемент управления button в <xref:System.Windows.Forms.TableLayoutPanel> первой ячейке элемента управления.  
  
3.  Дважды щелкните несколько других элементов управления в **панели элементов**. Обратите внимание, что новые элементы управления последовательно появляются в <xref:System.Windows.Forms.TableLayoutPanel> пустых ячейках элемента управления. Также Обратите внимание, что <xref:System.Windows.Forms.TableLayoutPanel> развертывания для размещения новых элементов управления, если доступны открытых ячеек элемента управления.  
  
## <a name="automatic-handling-of-overflows"></a>Автоматическая обработка переполнений  
 При вставке элементов управления в <xref:System.Windows.Forms.TableLayoutPanel> элемента управления, может не хватить пустые ячейки для новых элементов управления. <xref:System.Windows.Forms.TableLayoutPanel> Управления автоматически обрабатывает эту ситуацию, увеличив количество ячеек.  
  
#### <a name="to-observe-automatic-handling-of-overflows"></a>Чтобы наблюдать автоматическую обработку переполнений  
  
1.  Если по-прежнему пустые ячейки в <xref:System.Windows.Forms.TableLayoutPanel> управления, продолжите вставлять новые <xref:System.Windows.Forms.Button> управляет до <xref:System.Windows.Forms.TableLayoutPanel> заполнения элемента управления.  
  
2.  Один раз <xref:System.Windows.Forms.TableLayoutPanel> заполнения элемента управления, дважды щелкните <xref:System.Windows.Forms.Button> значок в **элементов** для вставки другой <xref:System.Windows.Forms.Button> элемента управления. Обратите внимание, что <xref:System.Windows.Forms.TableLayoutPanel> элемент управления создает новые ячейки для размещения нового элемента управления. Вставьте еще несколько элементов управления и пронаблюдайте, каким образом.  
  
3.  Измените значение свойства <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> элемента управления <xref:System.Windows.Forms.TableLayoutPanel> на <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>. Дважды щелкните <xref:System.Windows.Forms.Button> значок в **элементов** для вставки <xref:System.Windows.Forms.Button> управляет до <xref:System.Windows.Forms.TableLayoutPanel> заполнения элемента управления. Дважды щелкните <xref:System.Windows.Forms.Button> значок в **элементов** еще раз. Обратите внимание, что появляется сообщение об ошибке от **конструктор Windows Forms** о том, созданы дополнительные строки и столбцы.  
  
## <a name="inserting-a-control-by-drawing-its-outline"></a>Вставка элемента управления путем рисования его контура  
 Можно вставить элемент управления в <xref:System.Windows.Forms.TableLayoutPanel> управления и задать его размер, нарисовав его контур в ячейке.  
  
#### <a name="to-insert-a-control-by-drawing-its-outline"></a>Вставка элемента управления путем рисования его контура  
  
1.  Перетащите <xref:System.Windows.Forms.TableLayoutPanel> управления из **элементов** на форму.  
  
2.  В **панели элементов**щелкните значок элемента управления <xref:System.Windows.Forms.Button> . Не перетаскивайте его в форму.  
  
3.  Наведите указатель мыши на <xref:System.Windows.Forms.TableLayoutPanel> элемента управления. Обратите внимание, что указатель превратился в перекрестие с прикрепленным значком элемента управления <xref:System.Windows.Forms.Button> .  
  
4.  Нажмите и удерживайте кнопку мыши.  
  
5.  Перемещайте указатель мыши, чтобы нарисовать контур элемента управления <xref:System.Windows.Forms.Button> . Когда вас устроит размер, отпустите кнопку мыши. Обратите внимание, что <xref:System.Windows.Forms.Button> создается элемент управления в ячейке, в котором нарисован контур элемента управления.  
  
## <a name="multiple-controls-within-cells-are-not-permitted"></a>Несколько элементов управления внутри ячеек не допускаются.  
 <xref:System.Windows.Forms.TableLayoutPanel> Элемент управления может содержать только один дочерний элемент управления в ячейке.  
  
#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>Для демонстрации нескольких элементов управления внутри ячеек не разрешены  
  
-   Перетащите <xref:System.Windows.Forms.Button> управления из **элементов** в <xref:System.Windows.Forms.TableLayoutPanel> управления и вставьте его в одну из заполненных ячеек. Обратите внимание, что <xref:System.Windows.Forms.TableLayoutPanel> управления не разрешает удалять <xref:System.Windows.Forms.Button> элемента управления в заполненную ячейку.  
  
## <a name="swapping-controls"></a>Перестановки элементов управления  
 <xref:System.Windows.Forms.TableLayoutPanel> Позволяет поменять местами элементы управления, занимающих две разные ячейки.  
  
#### <a name="to-swap-controls"></a>Поменять местами элементы управления  
  
-   Перетащите один из <xref:System.Windows.Forms.Button> элементы управления из заполненную ячейку и drop в другую ячейку занято. Обратите внимание, что два элемента управления перемещаются из одной ячейки в другую.  
  
## <a name="next-steps"></a>Следующие шаги  
 Используя сочетание панелей макета и элементов управления, можно создавать сложные макеты. Рекомендуется также дополнительно исследовать следующие моменты.  
  
-   Попробуйте <xref:System.Windows.Forms.Button> элементы управления для большего размера и Примечание отразится на макете.  
  
-   Вставьте несколько выбранных элементов в <xref:System.Windows.Forms.TableLayoutPanel> управления и обратите внимание на то, как они вставляются.  
  
-   Панели макета могут содержать другие панели макета. Попробуйте вставить элемент управления <xref:System.Windows.Forms.TableLayoutPanel> в существующий элемент управления.  
  
-   Закрепление <xref:System.Windows.Forms.TableLayoutPanel> родительский элемент управления. Измените размер этой формы и обратите внимание, как это отражается на макете.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Взаимодействие с пользователем в Microsoft Windows, официальные рекомендации для разработчиков и конструкторов пользовательских интерфейсов. Redmond, WA: Microsoft Press, 1999 г. (USBN: 0-7356-0566-1)](http://www.microsoft.com/mspress/southpacific/books/book11588.htm)  
 [Пошаговое руководство. Создание в Windows Forms формы для ввода данных переменного размера](http://msdn.microsoft.com/library/e193b4fc-912a-4917-b036-b76c7a6f58ab)  
 [Пошаговое руководство: Создание локализации Windows Form](http://msdn.microsoft.com/library/c5240b6e-aaca-4286-9bae-778a416edb9c)  
 [Советы по использованию элемента управления TableLayoutPanel](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)  
 [Свойство AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Практическое руководство. Закрепление элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [Практическое руководство. Привязка элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)  
 [Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств Padding, Margins и AutoSize](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
