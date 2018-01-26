---
title: "Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств \"Padding\", \"Margins\" и \"AutoSize\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ccd5379d9594ccab02b80fd5fbdba0b202e1c69
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-laying-out-windows-forms-controls-with-padding-margins-and-the-autosize-property"></a>Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств "Padding", "Margins" и "AutoSize"
Точное расположение элементов управления на форме является важным для многих приложений. **Конструктор Windows Forms** дает много инструментов для выполнения этой задачи. Три наиболее важными являются <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, и <xref:System.Windows.Forms.Control.AutoSize%2A> свойства, которые присутствуют на все элементы управления Windows Forms.  
  
 Свойство <xref:System.Windows.Forms.Control.Margin%2A> определяет поле вокруг элемента управления, благодаря которому обеспечивается определенное расстояние между границами этого элемента и другими элементами.  
  
 Свойство <xref:System.Windows.Forms.Control.Padding%2A> определяет поле внутри элемента управления, благодаря которому обеспечивается определенное расстояние между содержимым элемента управления (например, значением свойства <xref:System.Windows.Forms.Control.Text%2A>) и его границами.  
  
 На рисунке ниже демонстрируется значение свойств <xref:System.Windows.Forms.Control.Padding%2A> и <xref:System.Windows.Forms.Control.Margin%2A> элемента управления.  
  
 ![Поля и заполнение для Windows Forms, элементы управления](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")  
  
 <xref:System.Windows.Forms.Control.AutoSize%2A> Свойство сообщает автоматическое изменение размера содержимого элемента управления. Его размер не будет меньше, чем исходного значения <xref:System.Windows.Forms.Control.Size%2A> свойство и его будет учитывать значение его <xref:System.Windows.Forms.Control.Padding%2A> свойство.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Создание проекта Windows Forms  
  
-   Установка полей для элементов управления  
  
-   Установка заполнения элементов управления  
  
-   Автоматическое изменение размеров элементов управления  
  
 После завершения вы будете понимать роль, которую играют эти важные функции макета.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения данного пошагового руководства требуется:  
  
-   Разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, где установлена среда Visual Studio.  
  
## <a name="creating-the-project"></a>Создание проекта  
 Первым шагом является создание проекта и настройка формы.  
  
#### <a name="to-create-the-project"></a>Создание проекта  
  
1.  Создание **приложение Windows** проект с именем `LayoutExample`. Дополнительные сведения см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) .  
  
2.  Выберите форму в **конструктор Windows Forms**.  
  
## <a name="setting-margins-for-your-controls"></a>Установка полей для элементов управления  
 Можно задать по умолчанию расстояние между элементами управления с помощью <xref:System.Windows.Forms.Control.Margin%2A> свойство. При перемещении элемента управления как можно ближе к другому элементу управления, то появится линия привязки, показывающая границы для двух элементов управления. Перемещаемый элемент управления будет привязан к определенному границами поля.  
  
#### <a name="to-arrange-controls-on-your-form-using-the-margin-property"></a>Размещение элементов управления в форме с помощью свойства поля  
  
1.  Перетащите два <xref:System.Windows.Forms.Button> управляет из **элементов** на форму.  
  
2.  Выберите один из <xref:System.Windows.Forms.Button> элементов управления и переместите его к другому, пока они почти соприкасаются.  
  
     Просмотрите привязки между ними. Это расстояние складывается из двух элементов управления <xref:System.Windows.Forms.Control.Margin%2A> значения. Это расстояние будет привязан элемент управления, который нужно переместить. Дополнительные сведения см. в разделе [Пошаговое руководство: упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
3.  Изменение <xref:System.Windows.Forms.Control.Margin%2A> свойство одного из элементов управления, развернув <xref:System.Windows.Forms.Control.Margin%2A> входа в **свойства** и установив <xref:System.Windows.Forms.Padding.All%2A> до 20.  
  
4.  Выберите один из <xref:System.Windows.Forms.Button> элементы управления, и перетащите его к другому.  
  
     Линии привязки определение сумма значений полей длиннее и элемент управления привязывается к больше расстояние от другого элемента управления.  
  
5.  Изменение <xref:System.Windows.Forms.Control.Margin%2A> свойства выбранного элемента управления, развернув <xref:System.Windows.Forms.Control.Margin%2A> входа в **свойства** и установив <xref:System.Windows.Forms.Padding.Top%2A> значение 5.  
  
6.  Переместите выбранный элемент управления под другой элемент управления и обратите внимание на более короткие линии привязки. Переместите выбранный элемент управления слева от другого элемента управления и обратите внимание, что линии привязки сохраняет значение, наблюдаемое в шаге 4.  
  
7.  Можно задать каждый из аспектов <xref:System.Windows.Forms.Control.Margin%2A> свойство, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, чтобы разные значения, или задать их все в то же значение с <xref:System.Windows.Forms.Padding.All%2A> свойство.  
  
## <a name="setting-padding-for-your-controls"></a>Установка заполнения элементов управления  
 Для получения точного макета, необходимый для приложения, элементы управления будут часто содержат дочерние элементы управления. Если вы хотите определить расстояние между границей дочернего элемента управления к границе родительского элемента управления, используйте родительского элемента управления <xref:System.Windows.Forms.Control.Padding%2A> свойства в сочетании с дочерним элементом управления <xref:System.Windows.Forms.Control.Margin%2A> свойство. <xref:System.Windows.Forms.Control.Padding%2A> Свойство также используется для управления расстоянием между содержимым элемента управления (например, <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Text%2A> свойства) и его границами.  
  
#### <a name="to-arrange-controls-on-your-form-using-padding"></a>Размещение элементов управления в форме с помощью заполнения  
  
1.  Перетащите <xref:System.Windows.Forms.Button> управления из **элементов** на форму.  
  
2.  Измените значение свойства <xref:System.Windows.Forms.Control.AutoSize%2A> элемента управления <xref:System.Windows.Forms.Button> на `true`.  
  
3.  Изменение <xref:System.Windows.Forms.Control.Padding%2A> , развернув <xref:System.Windows.Forms.Control.Padding%2A> входа в **свойства** и установив <xref:System.Windows.Forms.Padding.All%2A> значение 5.  
  
     Элемент управления расширяется, чтобы выделить место для новых внутренних полей.  
  
4.  Перетащите <xref:System.Windows.Forms.GroupBox> управления из **элементов** на форму. Перетащите <xref:System.Windows.Forms.Button> управления из **элементов** в <xref:System.Windows.Forms.GroupBox> элемента управления. Позиция <xref:System.Windows.Forms.Button> управления его записи на диск с в правом нижнем углу <xref:System.Windows.Forms.GroupBox> элемента управления.  
  
     Обратите внимание на линии привязки, как <xref:System.Windows.Forms.Button> управления приближается к нижней и правой границ <xref:System.Windows.Forms.GroupBox> элемента управления. Эти линии привязки соответствуют <xref:System.Windows.Forms.Control.Margin%2A> свойство <xref:System.Windows.Forms.Button>.  
  
5.  Изменение <xref:System.Windows.Forms.GroupBox> элемента управления <xref:System.Windows.Forms.Control.Padding%2A> , развернув <xref:System.Windows.Forms.Control.Padding%2A> входа в **свойства** и установив <xref:System.Windows.Forms.Padding.All%2A> до 20.  
  
6.  Выберите <xref:System.Windows.Forms.Button> управления в пределах <xref:System.Windows.Forms.GroupBox> управления и переместить его к центру <xref:System.Windows.Forms.GroupBox>.  
  
     Линии привязки появятся на большем расстоянии от границ элемента <xref:System.Windows.Forms.GroupBox> элемента управления. Это расстояние равно сумме <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Margin%2A> свойство и <xref:System.Windows.Forms.GroupBox> элемента управления <xref:System.Windows.Forms.Control.Padding%2A> свойство.  
  
## <a name="automatically-sizing-your-controls"></a>Автоматическое изменение размеров элементов управления  
 В некоторых приложениях размер элемента управления будут одинаковыми на время выполнения во время разработки. Текст <xref:System.Windows.Forms.Button> элемента управления, например, могут быть извлечены из базы данных, а его длина не будет известен заранее.  
  
 Когда <xref:System.Windows.Forms.Control.AutoSize%2A> свойству `true`, изменится на его содержимое размер элемента управления. Дополнительные сведения см. в разделе [Общие](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
#### <a name="to-arrange-controls-on-your-form-using-the-autosize-property"></a>Размещение элементов управления на форме с помощью свойства AutoSize  
  
1.  Перетащите <xref:System.Windows.Forms.Button> управления из **элементов** на форму.  
  
2.  Измените значение свойства <xref:System.Windows.Forms.Control.AutoSize%2A> элемента управления <xref:System.Windows.Forms.Button> на `true`.  
  
3.  Изменение <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Text%2A> свойства «**на этой кнопке изображен длинную строку для свойства Text**.»  
  
     При фиксации изменений, <xref:System.Windows.Forms.Button> элемента управления изменяется автоматически, чтобы вместить новый текст.  
  
4.  Перетащите еще одно <xref:System.Windows.Forms.Button> управления из **элементов** на форму.  
  
5.  Изменение <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Text%2A> свойства «**на этой кнопке изображен длинную строку для свойства Text.**»  
  
     При фиксации изменений, <xref:System.Windows.Forms.Button> сам не размеры элемента управления, и текст будет обрезан правой границе элемента управления.  
  
6.  Изменение <xref:System.Windows.Forms.Control.Padding%2A> , развернув <xref:System.Windows.Forms.Control.Padding%2A> входа в **свойства** и установив <xref:System.Windows.Forms.Padding.All%2A> значение 5.  
  
     Все четыре стороны обрезается текст элемента управления.  
  
7.  Изменение <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.AutoSize%2A> свойства `true`.  
  
     <xref:System.Windows.Forms.Button> Элемента управления изменяется автоматически, чтобы помещалась вся строка. Кроме того, были добавлены заполнения вокруг текста, вызывая <xref:System.Windows.Forms.Button> элемента управления, чтобы развернуть во всех четырех направлениях.  
  
8.  Перетащите <xref:System.Windows.Forms.Button> управления из **элементов** на форму. Поместите его в правом нижнем углу формы.  
  
9. Измените значение свойства <xref:System.Windows.Forms.Control.AutoSize%2A> элемента управления <xref:System.Windows.Forms.Button> на `true`.  
  
10. Задать <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Anchor%2A> свойства <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.  
  
11. Изменение <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Text%2A> свойства «**на этой кнопке изображен длинную строку для свойства Text.**»  
  
     При фиксации изменений, <xref:System.Windows.Forms.Button> элемент управления может изменять свои размеры налево. Как правило, автоматическое изменение размеров приведет к увеличению размера элемента управления в направлении, противоположном его <xref:System.Windows.Forms.Control.Anchor%2A> значение свойства.  
  
## <a name="autosize-and-autosizemode-properties"></a>AutoSize и свойства AutoSizeMode  
 Некоторые элементы управления поддерживают `AutoSizeMode` свойство, которое дает более точный контроль над поведение автоматического изменения размеров элемента управления.  
  
#### <a name="to-use-the-autosizemode-property"></a>Чтобы использовать AutoSizeMode-свойство  
  
1.  Перетащите <xref:System.Windows.Forms.Panel> управления из **элементов** на форму.  
  
2.  Установите для параметра <xref:System.Windows.Forms.Panel> элемента управления <xref:System.Windows.Forms.Control.AutoSize%2A> свойства `true`.  
  
3.  Перетащите <xref:System.Windows.Forms.Button> управления из **элементов** в <xref:System.Windows.Forms.Panel> элемента управления.  
  
4.  Место <xref:System.Windows.Forms.Button> управления в правом нижнем углу <xref:System.Windows.Forms.Panel> элемента управления.  
  
5.  Выберите <xref:System.Windows.Forms.Panel> управления и захватите правый нижний маркер. Изменить размер <xref:System.Windows.Forms.Panel> управления, чтобы увеличить и уменьшить.  
  
    > [!NOTE]
    >  Вы можете свободно изменять размер <xref:System.Windows.Forms.Panel> управления, но размер нельзя установить меньше, чем положение <xref:System.Windows.Forms.Button> правый нижний угол элемента управления. Такое поведение определяется по значению по умолчанию `AutoSizeMode` свойство, которое является <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.  
  
6.  Установите для параметра <xref:System.Windows.Forms.Panel> элемента управления `AutoSizeMode` свойства <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.  
  
     <xref:System.Windows.Forms.Panel> Размера элемента управления вокруг <xref:System.Windows.Forms.Button> элемента управления. Не удается изменить размер <xref:System.Windows.Forms.Panel> элемента управления.  
  
7.  Перетащите <xref:System.Windows.Forms.Button> управления сторону в верхнем левом углу <xref:System.Windows.Forms.Panel> элемента управления.  
  
     <xref:System.Windows.Forms.Panel> Управления изменяет свой размер <xref:System.Windows.Forms.Button> новое положение элемента управления.  
  
## <a name="next-steps"></a>Следующие шаги  
 Существует множество возможностей компоновки для упорядочивания элементов управления в приложениях Windows Forms. Ниже приведены некоторые сочетания, которые можно попробовать.  
  
-   Создайте форму с помощью <xref:System.Windows.Forms.TableLayoutPanel> элемента управления. Дополнительные сведения см. в разделе [Пошаговое руководство: упорядочение элементов управления в Windows Forms с помощью элемента TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md). Попробуйте изменить значения <xref:System.Windows.Forms.TableLayoutPanel> элемента управления <xref:System.Windows.Forms.Control.Padding%2A> свойства, а также <xref:System.Windows.Forms.Control.Margin%2A> свойства дочерних элементов управления.  
  
-   Повторите ту же эксперимент с помощью <xref:System.Windows.Forms.FlowLayoutPanel> элемента управления. Дополнительные сведения см. в разделе [Пошаговое руководство: упорядочение элементов управления в Windows Forms с помощью элемента FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
-   Поэкспериментируйте с закреплением дочерних элементов управления в <xref:System.Windows.Forms.Panel> элемента управления. <xref:System.Windows.Forms.Control.Padding%2A> Свойство является более общей реализацией <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> свойство и может выполнить самостоятельно, это условие выполняется, размещение дочернего элемента управления в <xref:System.Windows.Forms.Panel> управления и задание дочернего элемента управления <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Fill>. Задать <xref:System.Windows.Forms.Panel> элемента управления <xref:System.Windows.Forms.Control.Padding%2A> свойство различные значения и Примечание эффект.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>  
 <xref:System.Windows.Forms.Control.Margin%2A>  
 <xref:System.Windows.Forms.Control.Padding%2A>  
 [Свойство AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
