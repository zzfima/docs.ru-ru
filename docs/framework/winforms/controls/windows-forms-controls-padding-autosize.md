---
title: "Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств &quot;Padding&quot;, &quot;Margins&quot; и &quot;AutoSize&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Margin.Bottom"
  - "Margin.Left"
  - "Margin.Top"
  - "Margin.All"
  - "Margin.Right"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "AutoSize - свойство, пошаговые руководства"
  - "макет [Windows Forms], задание полей и интервалов"
  - "Margin - свойство [Windows Forms], пошаговые руководства"
  - "Padding - свойство [Windows Forms], пошаговые руководства"
  - "пошаговые руководства [Windows Forms], макет"
  - "Windows Forms, макет"
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 28
---
# Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств &quot;Padding&quot;, &quot;Margins&quot; и &quot;AutoSize&quot;
Точное расположение элементов управления на форме является важным для многих приложений.  **Конструктор Windows Forms** предоставляет широкий набор параметров макета, позволяющих выполнить эту задачу.  Тремя наиболее важными средствами являются свойства <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A> и <xref:System.Windows.Forms.Control.AutoSize%2A>, присутствующие у всех элементов управления Windows Forms.  
  
 Свойство <xref:System.Windows.Forms.Control.Margin%2A> определяет пространство вокруг элемента управления, которое обеспечивает определенное расстояние между границами этого элемента и другими элементами.  
  
 Свойство <xref:System.Windows.Forms.Control.Padding%2A> определяет пространство внутри элемента управления, которое обеспечивает определенное расстояние между содержимым элемента управления \(например значением свойства <xref:System.Windows.Forms.Control.Text%2A>\) и границами элемента управления.  
  
 На следующем рисунке показаны свойства <xref:System.Windows.Forms.Control.Padding%2A> и <xref:System.Windows.Forms.Control.Margin%2A> элемента управления.  
  
 ![Поля и заполнение для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS\_WinFormPadMargin")  
  
 Свойство <xref:System.Windows.Forms.Control.AutoSize%2A> включает автоматическое изменение размера элемента в соответствии с его содержимым.  Размер не будет установлен меньше исходного значения свойства <xref:System.Windows.Forms.Control.Size%2A>, а также будет учтено значение свойства <xref:System.Windows.Forms.Control.Padding%2A>.  
  
 В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   создание проекта типа Windows Forms;  
  
-   Установка полей элементов управления  
  
-   Установка заполнения элементов управления  
  
-   Автоматическое определение размеров элементов управления  
  
 По завершению процесса ознакомления вы получите представление о роли, которую играют эти важные средства работы с макетами.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Обязательные компоненты  
 Для выполнения этого пошагового руководства потребуется следующее.  
  
-   разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, на котором установлена Visual Studio.  
  
## Создание проекта  
 Для начала следует создать проект и подготовить форму.  
  
#### Создание проекта  
  
1.  Создайте проект **Приложение Windows** с именем `LayoutExample`.  Дополнительные сведения см. в разделе [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  В конструкторе **Windows Forms** выберите форму.  
  
## Установка полей элементов управления  
 Установить расстояние по умолчанию между элементами управления можно с помощью свойства <xref:System.Windows.Forms.Control.Margin%2A>.  При перемещении элемента управления достаточно близко к другому элементу управления появляется линия привязки, показывающая границы обоих элементов управления.  Перемещаемый элемент управления будет привязан к определенному границами расстоянию.  
  
#### Чтобы расположить элементы управления на форме с помощью свойства "Margin"  
  
1.  Перетащите два элемента управления <xref:System.Windows.Forms.Button> из **панели элементов** в форму.  
  
2.  Выберите один из элементов управления <xref:System.Windows.Forms.Button> и приблизьте его к другому почти до касания.  
  
     Обратите внимание на линию привязки, которая появится между ними.  Это расстояние определяется суммой значений свойства <xref:System.Windows.Forms.Control.Margin%2A> двух элементов управления.  Перемещаемый элемент управления будет привязан к этому расстоянию.  Дополнительные сведения см. в разделе [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
3.  Измените свойство <xref:System.Windows.Forms.Control.Margin%2A> одного из элементов управления, развернув пункт <xref:System.Windows.Forms.Control.Margin%2A> в окне **Свойства**, и установив значение свойства <xref:System.Windows.Forms.Padding.All%2A> равным 20.  
  
4.  Выберите один из элементов управления <xref:System.Windows.Forms.Button> и приблизьте его к другому.  
  
     Линия привязки, определяющая сумму значений полей, длиннее. И элемент управления привязывается на большем расстоянии от другого элемента управления.  
  
5.  Измените свойство <xref:System.Windows.Forms.Control.Margin%2A> выбранного элемента управления, развернув пункт <xref:System.Windows.Forms.Control.Margin%2A> в окне **Свойства**, и установив значение свойства <xref:System.Windows.Forms.Padding.Top%2A> равным 5.  
  
6.  Переместите выбранный элемент управления под другой элемент управления и обратите внимание на то, что линия привязки будет короче.  Переместите выбранный элемент управления слева от другого элемента управления и обратите внимание на то, что линия привязки будет такой же, как на этапе 4.  
  
7.  Можно установить разные значения для каждого из параметров свойства <xref:System.Windows.Forms.Control.Margin%2A> — <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A> — или можно установить единое значение для всех этих параметров с помощью свойства <xref:System.Windows.Forms.Padding.All%2A>.  
  
## Установка заполнения элементов управления  
 Для создания точного макета в соответствии с требованиями приложения элементы управления часто содержат дочерние элементы управления.  При необходимости определить расстояние между границами дочернего и родительского элемента управления используйте свойство <xref:System.Windows.Forms.Control.Padding%2A> родительского элемента управления в сочетании со свойством <xref:System.Windows.Forms.Control.Margin%2A> дочернего элемента управления.  Свойство <xref:System.Windows.Forms.Control.Padding%2A> также используется для управления расстоянием между содержимым элемента управления \(например свойством <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.Button>\) и его границами.  
  
#### Чтобы расположить элементы управления на форме с помощью свойства "Padding"  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в форму.  
  
2.  Измените значение свойства <xref:System.Windows.Forms.Control.AutoSize%2A> элемента управления <xref:System.Windows.Forms.Button> на `true`.  
  
3.  Измените свойство <xref:System.Windows.Forms.Control.Padding%2A>, развернув пункт <xref:System.Windows.Forms.Control.Padding%2A> в окне **Свойства**, и установив значение свойства <xref:System.Windows.Forms.Padding.All%2A> равным 5.  
  
     Элемент управления расширится, чтобы обеспечить необходимое пространство для новых внутренних полей.  
  
4.  Перетащите элемент управления <xref:System.Windows.Forms.GroupBox> из **панели элементов** в форму.  Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в элемент управления <xref:System.Windows.Forms.GroupBox>.  Расположите элемент управления <xref:System.Windows.Forms.Button>, совместив его с нижним правым углом элемента управления <xref:System.Windows.Forms.GroupBox>.  
  
     Обратите внимание на линию привязки, которая появится при приближении элемента управления <xref:System.Windows.Forms.Button> к нижней и правой границе элемента управления <xref:System.Windows.Forms.GroupBox>.  Эти линии привязки соответствуют свойству <xref:System.Windows.Forms.Control.Margin%2A> элемента управления <xref:System.Windows.Forms.Button>.  
  
5.  Измените свойство <xref:System.Windows.Forms.Control.Padding%2A> элемента управления <xref:System.Windows.Forms.GroupBox>, развернув пункт <xref:System.Windows.Forms.Control.Padding%2A> в окне **Свойства** и установив значение свойства <xref:System.Windows.Forms.Padding.All%2A> равным 20.  
  
6.  Выберите элемент управления <xref:System.Windows.Forms.Button> внутри элемента управления <xref:System.Windows.Forms.GroupBox> и переместите его к центру <xref:System.Windows.Forms.GroupBox>.  
  
     Линии привязки появятся на большем расстоянии от границ элемента управления <xref:System.Windows.Forms.GroupBox>.  Это расстояние определяется суммой значений свойства <xref:System.Windows.Forms.Control.Margin%2A> элемента управления <xref:System.Windows.Forms.Button> и свойства <xref:System.Windows.Forms.Control.Padding%2A> элемента управления <xref:System.Windows.Forms.GroupBox>.  
  
## Автоматическое определение размеров элементов управления  
 В некоторых приложениях размер элемента управления во время выполнения и во время разработки отличается.  Например, текст элемента управления <xref:System.Windows.Forms.Button> может извлекаться из базы данных, и его длина не будет известна заранее.  
  
 Когда свойству <xref:System.Windows.Forms.Control.AutoSize%2A> присвоено значение `true`, размер элемента управления изменяется автоматически в соответствии с его содержимым.  Дополнительные сведения см. в разделе [Свойство AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
#### Чтобы расположить элементы управления на форме с помощью свойства AutoSize  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в форму.  
  
2.  Измените значение свойства <xref:System.Windows.Forms.Control.AutoSize%2A> элемента управления <xref:System.Windows.Forms.Button> на `true`.  
  
3.  Измените свойство <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.Button> на "Эта кнопка содержит длинную строку для свойства Text".  
  
     После внесения изменений размер элемента управления <xref:System.Windows.Forms.Button> будет изменен автоматически в соответствии с новым текстом.  
  
4.  Перетащите еще один элемент управления <xref:System.Windows.Forms.Button> с **панели элементов** на форму.  
  
5.  Измените свойство <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.Button> на "Эта кнопка содержит длинную строку для свойства Text".  
  
     После применения изменения размер элемента управления <xref:System.Windows.Forms.Button> не будет изменен автоматически, текст будет обрезан правой границе элемента управления.  
  
6.  Измените свойство <xref:System.Windows.Forms.Control.Padding%2A>, развернув пункт <xref:System.Windows.Forms.Control.Padding%2A> в окне **Свойства**, и установив значение свойства <xref:System.Windows.Forms.Padding.All%2A> равным 5.  
  
     Текст внутри элемента управления обрезается со всех четырех сторон.  
  
7.  Измените свойство <xref:System.Windows.Forms.Control.AutoSize%2A> элемента управления <xref:System.Windows.Forms.Button> на `true`.  
  
     Размер элемента управления <xref:System.Windows.Forms.Button> изменяется автоматически, чтобы помещалась вся строка.  Кроме того, добавлены внутренние границы вокруг текста, за счет чего элемент управления <xref:System.Windows.Forms.Button> увеличился во всех четырех направлениях.  
  
8.  Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в форму.  Расположите его рядом с нижним правым углом формы.  
  
9. Измените значение свойства <xref:System.Windows.Forms.Control.AutoSize%2A> элемента управления <xref:System.Windows.Forms.Button> на `true`.  
  
10. Присвойте свойству <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления <xref:System.Windows.Forms.Button> значение <xref:System.Windows.Forms.AnchorStyles>, <xref:System.Windows.Forms.AnchorStyles>.  
  
11. Измените свойство <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.Button> на "Эта кнопка содержит длинную строку для свойства Text".  
  
     После применения изменения размер элемента управления <xref:System.Windows.Forms.Button> будет изменен автоматически влево.  Вообще, при автоматическом определении размеров увеличение размера элемента управления происходит в направлении, противоположном установке <xref:System.Windows.Forms.Control.Anchor%2A>.  
  
## Свойства AutoSize и AutoSizeMode  
 Некоторые элементы управления поддерживают свойство `AutoSizeMode`, что обеспечивает более точное управление автоматическим определением размеров элемента управления.  
  
#### Чтобы использовать свойство AutoSizeMode  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.Panel> из **панели элементов** в форму.  
  
2.  Присвойте свойству <xref:System.Windows.Forms.Control.AutoSize%2A> элемента управления <xref:System.Windows.Forms.Panel> значение `true`.  
  
3.  Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в элемент управления <xref:System.Windows.Forms.Panel>.  
  
4.  Расположите элемент управления <xref:System.Windows.Forms.Button> рядом с нижним правым углом элемента управления <xref:System.Windows.Forms.Panel>.  
  
5.  Выберите элемент управления <xref:System.Windows.Forms.Panel> и возьмитесь за нижний правый маркер изменения размера.  Попробуйте увеличить и уменьшить размер элемента управления <xref:System.Windows.Forms.Panel>.  
  
    > [!NOTE]
    >  Размер элемента управления <xref:System.Windows.Forms.Panel> можно изменять свободно, но размер нельзя установить меньше положения нижнего правого угла элемента управления <xref:System.Windows.Forms.Button>.  Такое поведение определяется значением свойства `AutoSizeMode` по умолчанию — <xref:System.Windows.Forms.AutoSizeMode>.  
  
6.  Присвойте свойству `AutoSizeMode` элемента управления <xref:System.Windows.Forms.Panel> значение <xref:System.Windows.Forms.AutoSizeMode>.  
  
     Размеры элемента управления <xref:System.Windows.Forms.Panel> определяются автоматически для окружения элемента управления <xref:System.Windows.Forms.Button>.  Размеры элемента управления <xref:System.Windows.Forms.Panel> изменить нельзя.  
  
7.  Перетащите элемент управления <xref:System.Windows.Forms.Button> к верхнему левому углу элемента управления <xref:System.Windows.Forms.Panel>.  
  
     Размер элемента управления <xref:System.Windows.Forms.Panel> изменится в соответствии с новым положением элемента управления <xref:System.Windows.Forms.Button>.  
  
## Следующие действия  
 Для упорядочивания элементов управления приложений Windows Forms есть также много других возможностей форматирования.  Ниже приведено несколько комбинаций, которые можно попробовать.  
  
-   Постройте форму с помощью элемента управления<xref:System.Windows.Forms.TableLayoutPanel> control.  Дополнительные сведения см. в разделе [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  Попробуйте изменить значения свойства <xref:System.Windows.Forms.Control.Padding%2A> элемента управления <xref:System.Windows.Forms.TableLayoutPanel>, а также свойства <xref:System.Windows.Forms.Control.Margin%2A> дочерних элементов управления.  
  
-   Попробуйте выполнить тот же эксперимент с помощью элемента управления <xref:System.Windows.Forms.FlowLayoutPanel>.  Дополнительные сведения см. в разделе [Пример. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
-   Поэкспериментируйте с закреплением дочерних элементов управления в элементе управления <xref:System.Windows.Forms.Panel>.  Свойство <xref:System.Windows.Forms.Control.Padding%2A> является более общей реализацией свойства <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>. Вы можете убедиться в этом, поместив дочерний элемент управления в элемент управления <xref:System.Windows.Forms.Panel> и присвоив свойству <xref:System.Windows.Forms.Control.Dock%2A> дочернего элемента управления свойство <xref:System.Windows.Forms.DockStyle>.  Присвойте свойству <xref:System.Windows.Forms.Control.Padding%2A> элемента управления <xref:System.Windows.Forms.Panel> различные значения и обратите внимание на производимый изменениями эффект.  
  
## См. также  
 <xref:System.Windows.Forms.Control.AutoSize%2A>   
 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>   
 <xref:System.Windows.Forms.Control.Margin%2A>   
 <xref:System.Windows.Forms.Control.Padding%2A>   
 [Свойство AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)