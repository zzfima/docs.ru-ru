---
title: "Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления [Windows Forms], упорядочение с помощью TableLayoutPanel"
  - "TableLayoutPanel - элемент управления [Windows Forms], пошаговые руководства"
  - "элементы управления Windows Forms, упорядочение"
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 28
---
# Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel
Для некоторых приложений требуется форма, макет которой самостоятельно перестраивается соответствующим образом при изменении размера формы или размера содержимого.  Чтобы использовать динамический макет, но не обрабатывать явно в коде события <xref:System.Windows.Forms.Control.Layout>, следует использовать панель макета.  
  
 Элементы управления <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel> предоставляют простые способы организации элементов управления в форме.  Оба они предлагают автоматическую настраиваемую возможность управлять относительным положением дочерних элементов управления внутри них и использовать возможности динамического макета во время выполнения, то есть они могут изменять размер и положение дочерних элементов управления при изменении размеров родительской формы.  Панели макетов можно вкладывать в другие панели макетов, что обеспечивает реализацию сложных пользовательских интерфейсов.  
  
 Элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает свое содержимое в горизонтальном или вертикальном направлении.  Его содержимое может переноситься из одной строки или столбца в следующий.  Кроме того, вместо переноса содержимое может обрезаться.  Дополнительные сведения см. в разделе [Пример. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
 Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> располагает содержимое в виде сетки, что обеспечивает функциональные возможности, аналогичные HTML\-элементу \<table\>.  Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> позволяет размещать элементы управления в виде сетки, при этом не требуется точно указывать положение каждого отдельного элемента управления.  Его ячейки организованы в виде строк и столбцов, и они могут быть разного размера.  Ячейки можно объединять по строке или по столбцу.  Ячейки могут содержать все, что может содержаться в форме, и во многих отношениях они ведут себя как контейнеры.  
  
 Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> также предлагает возможность пропорционального изменения размера при выполнении, то есть при изменении размера формы макет может плавно изменяться.  Благодаря этому элемент управления <xref:System.Windows.Forms.TableLayoutPanel> хорошо подходит для форм ввода данных и локализованных приложений.  Дополнительные сведения см. в разделах [Walkthrough: Creating a Resizable Windows Form for Data Entry](http://msdn.microsoft.com/ru-ru/e193b4fc-912a-4917-b036-b76c7a6f58ab) и [Walkthrough: Creating a Localizable Windows Form](http://msdn.microsoft.com/ru-ru/c5240b6e-aaca-4286-9bae-778a416edb9c).  
  
 Как правило, не следует использовать элемент управления <xref:System.Windows.Forms.TableLayoutPanel> как контейнер для всего макета.  Для обеспечения возможностей пропорционального изменения размера частей макета используйте элементы управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   создание проекта типа Windows Forms;  
  
-   Расположение элементов управления по строкам и столбцам  
  
-   Задание свойств строк и столбцов  
  
-   Объединение строк и столбцов с помощью элемента управления  
  
-   Автоматическая обработка переполнений  
  
-   Вставка элементов управления двойным щелчком по ним в панели элементов  
  
-   Вставка элемента управления, обрисовывая его контур  
  
-   переназначение существующих элементов управления другому родительскому элементу  
  
 По завершению процесса ознакомления вы получите представление о роли, которую играют эти важные средства работы с макетами.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Создание проекта  
 Для начала следует создать проект и подготовить форму.  
  
#### Создание проекта  
  
1.  Создайте проект "Приложение Windows" с именем "TableLayoutPanelExample".  Дополнительные сведения см. в разделе [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Выберите форму в **Конструкторе** **Windows Forms**.  
  
## Расположение элементов управления по строкам и столбцам  
 Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> позволяет легко расположить элементы управления по строками или столбцам.  
  
#### Чтобы расположить элементы управления по строкам и столбцам, используя TableLayoutPanel  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в форму.  Обратите внимание, что по умолчанию в элементе управления <xref:System.Windows.Forms.TableLayoutPanel> содержатся четыре ячейки.  
  
2.  Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в элемент управления <xref:System.Windows.Forms.TableLayoutPanel> и вставьте его в одну из ячеек.  Обратите внимание, что элемент управления <xref:System.Windows.Forms.Button> создается внутри выбранной ячейки.  
  
3.  Перетащите еще три элемента управления <xref:System.Windows.Forms.Button> из **панели элементов** в элемент управления <xref:System.Windows.Forms.TableLayoutPanel>, чтобы в каждой ячейке появилась кнопка.  
  
4.  Захватите вертикальный маркер изменения размера между двумя столбцами и переместите его влево.  Обратите внимание, что элементы управления <xref:System.Windows.Forms.Button> в первом столбце становятся уже, а размер элементов управления <xref:System.Windows.Forms.Button> во втором столбце не меняется.  
  
5.  Захватите вертикальный маркер изменения размера между двумя столбцами и переместите его вправо.  Обратите внимание, что размер элементов управления <xref:System.Windows.Forms.Button> в первом столбце восстанавливается, а элементы управления <xref:System.Windows.Forms.Button> во втором столбце сдвигаются вправо.  
  
6.  Переместите горизонтальный маркер изменения размера вверх и вниз, чтобы понять, как это влияет на элементы управления в панели.  
  
## Расположение элементов управления внутри ячеек с использованием функций закрепления и привязки  
 Действие функции привязки на дочерние элементы управления в <xref:System.Windows.Forms.TableLayoutPanel> отличается от ее действия в других элементах управления контейнерного типа.  Действие функции закрепления для дочерних элементов управления аналогично ее действию для других элементов управления контейнерного типа.  
  
#### Размещение элементов управления внутри ячеек  
  
1.  Выберите первый элемент управления <xref:System.Windows.Forms.Button>.  Измените значение его свойства <xref:System.Windows.Forms.Control.Dock%2A> на <xref:System.Windows.Forms.DockStyle>.  Обратите внимание, что элемент управления <xref:System.Windows.Forms.Button> расширяется и полностью заполняет ячейку.  
  
2.  Выберите один из других элементов управления <xref:System.Windows.Forms.Button>.  Измените значение его свойства <xref:System.Windows.Forms.Control.Anchor%2A> на <xref:System.Windows.Forms.AnchorStyles>.  Обратите внимание, что он перемещается таким образом, что его правая граница располагается рядом с правой границей ячейки.  Расстояние между границами вычисляется как сумма свойства <xref:System.Windows.Forms.Control.Margin%2A> элемента управления <xref:System.Windows.Forms.Button> и свойства <xref:System.Windows.Forms.Control.Padding%2A> панели.  
  
3.  Измените значение свойства <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> на <xref:System.Windows.Forms.AnchorStyles> и <xref:System.Windows.Forms.AnchorStyles>.  Обратите внимание, что размер элемента управления подгоняется по ширине ячейки, причем во внимание принимаются значения <xref:System.Windows.Forms.Control.Margin%2A> и <xref:System.Windows.Forms.Control.Padding%2A>.  
  
4.  Повторите шаги 2 и 3, используя стили <xref:System.Windows.Forms.AnchorStyles> и <xref:System.Windows.Forms.AnchorStyles>.  
  
## Задание свойств строк и столбцов  
 Можно задать отдельные свойства строк и столбцов, используя коллекции <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> и <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>.  
  
#### Чтобы задать свойства строк и столбцов  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> в **Конструкторе Windows Forms**.  
  
2.  В окне **Свойства** откройте коллекцию <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>, нажав кнопку ellipsis \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) рядом с записью **Столбцы**.  
  
3.  Выберите первый столбец и измените значение его свойства <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> на <xref:System.Windows.Forms.SizeType>.  Нажмите кнопку **ОК**, чтобы принять изменения.  Обратите внимание, что ширина первого столбца меняется для соответствия элементу управления <xref:System.Windows.Forms.Button>.  Также обратите внимание, что ширину столбца менять нельзя.  
  
4.  В окне **Свойства** откройте коллекцию <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> и выберите первый столбец.  Измените значение его свойства <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> на <xref:System.Windows.Forms.SizeType>.  Нажмите кнопку **ОК**, чтобы принять изменения.  Увеличьте ширину элемента управления <xref:System.Windows.Forms.TableLayoutPanel> и обратите внимание на увеличение ширины первого столбца.  Уменьшите ширину элемента управления <xref:System.Windows.Forms.TableLayoutPanel> и обратите внимание, что размер кнопок в первом столбце изменяется с учетом размера ячейки.  Также обратите внимание, что можно менять ширину столбца.  
  
5.  В окне **Свойства** откройте коллекцию <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> и выберите все перечисленные столбцы.  Присвойте свойству <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> всех элементов управления значение <xref:System.Windows.Forms.SizeType>.  Нажмите кнопку **ОК**, чтобы принять изменения.  Повторите процедуру, используя коллекцию <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A>.  
  
6.  Потяните за один из угловых маркеров изменения размера и измените ширину и высоту элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  Обратите внимание на изменение размеров строк и столбцов при изменении размера элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  Также обратите внимание, что можно менять размер строк и столбцов при помощи вертикальных и горизонтальных маркеров изменения размера.  
  
## Объединение строк и столбцов с помощью элемента управления  
 Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> добавляет несколько новых свойств, применимых к элементам управления во время разработки.  К ним относятся свойства `RowSpan` и `ColumnSpan`.  Можно использовать эти свойства, чтобы элемент управления относился к нескольким столбцам или строкам.  
  
#### Чтобы объединить строки и столбцы с помощью элемента управления  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.Button> в первой строке первого столбца.  
  
2.  В окнах **Свойства** измените значение свойства `ColumnSpan` на 2.  Обратите внимание, что элемент управления <xref:System.Windows.Forms.Button> теперь охватывает первый и второй столбцы.  Также обратите внимание, что при этом добавляется дополнительная строка, учитывающая это изменение.  
  
3.  Повторите шаг 2 для свойства `RowSpan`.  
  
## Вставка элементов управления двойным щелчком по ним в панели элементов  
 Можно заполнять элемент управления <xref:System.Windows.Forms.TableLayoutPanel> двойным щелчком по элементам управления в **панели элементов**.  
  
#### Чтобы вставить элементы управления двойным щелчком по ним в панели элементов  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в форму.  
  
2.  Дважды щелкните значок элемента управления <xref:System.Windows.Forms.Button> на **панели элементов**.  Обратите внимание на появление нового кнопочного элемента управления в первой ячейке элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
3.  Дважды щелкните несколько других элементов управления в **панели элементов**.  Обратите внимание, что новые элементы управления последовательно появляются в пустых ячейках элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  Также обратите внимание, что при недоступности открытых ячеек элемент управления <xref:System.Windows.Forms.TableLayoutPanel> расширяется, чтобы вместить новые элементы управления.  
  
## Автоматическая обработка переполнений  
 При вставке элементов управления в элемент управления <xref:System.Windows.Forms.TableLayoutPanel> могут закончиться пустые ячейки для новых элементов управления.  Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> автоматически обрабатывает эту ситуацию, увеличивая число ячеек.  
  
#### Чтобы наблюдать автоматическую обработку переполнений  
  
1.  Если в элементе управления <xref:System.Windows.Forms.TableLayoutPanel> есть пустые ячейки, продолжите вставлять новые элементы управления <xref:System.Windows.Forms.Button> до заполнения элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
2.  После заполнения элемента управления <xref:System.Windows.Forms.TableLayoutPanel> дважды щелкните значок <xref:System.Windows.Forms.Button> на **панели элементов**, чтобы вставить еще один элемент управления <xref:System.Windows.Forms.Button>.  Обратите внимание, что в элементе управления <xref:System.Windows.Forms.TableLayoutPanel> создаются новые ячейки для размещения новых элементов управления.  Вставьте еще несколько элементов управления и пронаблюдайте, каким образом выполняется изменение размера.  
  
3.  Измените значение свойства <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> элемента управления <xref:System.Windows.Forms.TableLayoutPanel> на <xref:System.Windows.Forms.TableLayoutPanelGrowStyle>.  Дважды щелкните значок <xref:System.Windows.Forms.Button> на **панели элементов**, чтобы вставить элементы управления <xref:System.Windows.Forms.Button> до заполнения элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  Дважды щелкните значок элемента управления <xref:System.Windows.Forms.Button> на **панели элементов** еще раз.  Обратите внимание на сообщение об ошибке **Конструктора Windows Forms**, информирующее о невозможности создать дополнительные строки и столбцы.  
  
## Вставка элемента управления, обрисовывая его контур  
 Можно вставить элемент управления в элемент управления <xref:System.Windows.Forms.TableLayoutPanel> и указать его размер, нарисовав в ячейке его контур.  
  
#### Чтобы вставить элемент управления, обрисовывая его контур  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в форму.  
  
2.  На **панели элементов** щелкните значок элемента управления <xref:System.Windows.Forms.Button>.  Не перетаскивайте его в форму.  
  
3.  Наведите указатель мыши на элемент управления <xref:System.Windows.Forms.TableLayoutPanel>.  Обратите внимание, что указатель превращается в перекрестие, к которому прикреплен значок элемента управления <xref:System.Windows.Forms.Button>.  
  
4.  Нажмите и удерживайте кнопку мыши.  
  
5.  Перемещайте указатель мыши, рисуя контур элемента управления <xref:System.Windows.Forms.Button>.  При достижении требуемого размера отпустите кнопку мыши.  Обратите внимание, что в ячейке, где был нарисован контур элемента управления, создается элемент управления <xref:System.Windows.Forms.Button>.  
  
## Использование нескольких элементов управления в одной ячейке запрещено  
 В каждой ячейке элемента управления <xref:System.Windows.Forms.TableLayoutPanel> может содержаться только один дочерний элемент управления.  
  
#### Чтобы пронаблюдать невозможность использования нескольких элементов управления в одной ячейке  
  
-   Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в элемент управления <xref:System.Windows.Forms.TableLayoutPanel> и вставьте его в одну из заполненных ячеек.  Обратите внимание, что элемент управления <xref:System.Windows.Forms.TableLayoutPanel> не разрешает вставить элемент управления <xref:System.Windows.Forms.Button> в заполненную ячейку.  
  
## Перестановки элементов управления  
 Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> позволяет менять местами элементы управления, занимающие две разные ячейки.  
  
#### Чтобы поменять местами элементы управления  
  
-   Перетащите один из элементов управления <xref:System.Windows.Forms.Button> из занимаемой им ячейки в другую занятую ячейку.  Обратите внимание, как два элемента управления перемещаются из одной ячейки в другую.  
  
## Следующие действия  
 Используя сочетание панелей макета и элементов управления можно добиться создания сложных макетов.  Рекомендации по дальнейшему обучению.  
  
-   Попробуйте увеличить размер элементов управления <xref:System.Windows.Forms.Button> и пронаблюдайте воздействие этого действия на макет.  
  
-   Вставьте несколько выбранных элементов управления в элемент управления <xref:System.Windows.Forms.TableLayoutPanel> и пронаблюдайте, каким образом они вставляются.  
  
-   Панели макета могут содержать другие панели макета.  Попробуйте вставить элемент управления <xref:System.Windows.Forms.TableLayoutPanel> в существующий элемент управления.  
  
-   Закрепите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> в родительской форме.  Измените форму и пронаблюдайте изменения макета.  
  
## См. также  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Работа пользователей в ОС Microsoft Windows, официальные рекомендации для разработчиков и проектировщиков. Redmond, WA: Microsoft Press, 1999. \(USBN: 0\-7356\-0566\-1\)](http://www.microsoft.com/mspress/southpacific/books/book11588.htm)   
 [Walkthrough: Creating a Resizable Windows Form for Data Entry](http://msdn.microsoft.com/ru-ru/e193b4fc-912a-4917-b036-b76c7a6f58ab)   
 [Walkthrough: Creating a Localizable Windows Form](http://msdn.microsoft.com/ru-ru/c5240b6e-aaca-4286-9bae-778a416edb9c)   
 [Советы по использованию элемента управления TableLayoutPanel](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)   
 [Свойство AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [Практическое руководство. Закрепление элементов управления в формах Windows Forms.](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)   
 [Практическое руководство. Привязка элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)   
 [Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств "Padding", "Margins" и "AutoSize"](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)