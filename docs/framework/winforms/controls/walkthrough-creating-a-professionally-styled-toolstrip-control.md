---
title: "Пример. Создание профессионально оформленного элемента управления ToolStrip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3d47f285643f0b989db9419392eed736d0efbea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a>Пример. Создание профессионально оформленного элемента управления ToolStrip
Можно создать для своего приложения <xref:System.Windows.Forms.ToolStrip> управляет профессиональный внешний вид и поведение, создайте собственный класс, производный от <xref:System.Windows.Forms.ToolStripProfessionalRenderer> типа.  
  
 В этом пошаговом руководстве демонстрируется использование <xref:System.Windows.Forms.ToolStrip> элементы управления для создания составного элемента управления, напоминающего **панели навигации** в Microsoft® Outlook®. В этом пошаговом руководстве представлены следующие задачи:  
  
-   Создание проекта библиотеки элементов управления Windows.  
  
-   Проектирование StackView элемента управления.  
  
-   Реализация пользовательского средства отрисовки.  
  
 Когда вы закончите, будет иметь элемент управления для повторного использования пользовательских клиентских профессиональный внешний вид элемента управления Microsoft Office® XP.  
  
 Скопируйте код из этой темы, в разделе [как: создание профессионально оформленного элемента управления ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения данного пошагового руководства требуется:  
  
-   Разрешения, достаточные для создания и выполнения проектов приложений Windows Forms на компьютере, где [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] установлен.  
  
## <a name="creating-a-windows-control-library-project"></a>Создание проекта библиотеки элементов управления Windows  
 Первым шагом является создание проекта библиотеки элементов управления.  
  
#### <a name="to-create-the-control-library-project"></a>Создание проекта библиотеки элементов управления  
  
1.  Создайте новый проект библиотеки элементов управления Windows с именем `StackViewLibrary`.  
  
2.  В **обозревателе решений**, удалите элемент управления проекта по умолчанию, удаляя исходный файл «UserControl1.cs» или «UserControl1.vb» в зависимости от выбранного языка.  
  
     Дополнительные сведения см. в разделе [NIB: Практическое: удаление, Delete и исключить элементы](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
3.  Добавьте новый <xref:System.Windows.Forms.UserControl> элемент **StackViewLibrary** проекта. Присвойте имя базовой новый исходный файл `StackView`.  
  
## <a name="designing-the-stackview-control"></a>Проектирование элемента управления StackView  
 `StackView` Составной элемент управления, с одним дочерним <xref:System.Windows.Forms.ToolStrip> элемента управления. Дополнительные сведения о составных элементах управления см. в разделе [разновидности пользовательских элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).  
  
#### <a name="to-design-the-stackview-control"></a>Чтобы разработать элемент управления StackView  
  
1.  Из **элементов**, перетащите <xref:System.Windows.Forms.ToolStrip> управления на поверхность разработки.  
  
2.  В **свойства** задайте <xref:System.Windows.Forms.ToolStrip> свойства элемента управления в соответствии со следующей таблицей.  
  
    |Свойство.|Значение|  
    |--------------|-----------|  
    |name|`stackStrip`|  
    |CanOverflow|`false`|  
    |Закрепить|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |Шрифт|`Tahoma, 10pt, style=Bold`|  
    |Стиль захвата|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |Заполнение|`0, 7, 0, 0`|  
    |Отображается как|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3.  В конструкторе Windows Forms выберите <xref:System.Windows.Forms.ToolStrip> элемента управления **добавить** и добавьте <xref:System.Windows.Forms.ToolStripButton> для `stackStrip` элемента управления.  
  
4.  В **свойства** задайте <xref:System.Windows.Forms.ToolStripButton> свойства элемента управления в соответствии со следующей таблицей.  
  
    |Свойство.|Значение|  
    |--------------|-----------|  
    |name|`mailStackButton`|  
    |CheckOnClick|true|  
    |Свойство CheckState|<xref:System.Windows.Forms.CheckState.Checked>|  
    |DisplayStyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |ImageAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |ImageTransparentColor|`238, 238, 238`|  
    |Поля|`0, 0, 0, 0`|  
    |Заполнение|`3, 3, 3, 3`|  
    |Text|**Почта**|  
    |TextAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5.  Повторите шаг 7 для еще трех <xref:System.Windows.Forms.ToolStripButton> элементов управления.  
  
     Присвоение имен элементам управления `calendarStackButton`, `contactsStackButton`, и `tasksStackButton`. Установите для параметра <xref:System.Windows.Forms.Control.Text%2A> свойства **календаря**, **контактов**, и **задачи**соответственно.  
  
## <a name="handling-events"></a>Обработка событий  
 Чтобы сделать важны два события `StackView` корректного поведения элемента управления. Обрабатывать <xref:System.Windows.Forms.UserControl.Load> событий, чтобы правильно разместить элемент управления. Обрабатывать <xref:System.Windows.Forms.ToolStripItem.Click> событий для каждого <xref:System.Windows.Forms.ToolStripButton> для предоставления `StackView` контролировать состояние поведение аналогично <xref:System.Windows.Forms.RadioButton> элемента управления.  
  
#### <a name="to-handle-events"></a>Для обработки событий  
  
1.  В конструкторе Windows Forms выберите `StackView` элемента управления.  
  
2.  В **свойства** окно, нажмите кнопку **события**.  
  
3.  Дважды щелкните событие загрузки для создания `StackView_Load` обработчика событий.  
  
4.  Скопируйте и вставьте в обработчике события `StackView_Load` следующий код.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  В конструкторе Windows Forms выберите `mailStackButton` элемента управления.  
  
6.  В **свойства** окно, нажмите кнопку **события**.  
  
7.  Дважды щелкните событие Click.  
  
     Конструктор Windows Forms создает `mailStackButton_Click` обработчика событий.  
  
8.  Переименуйте `mailStackButton_Click` обработчик событий `stackButton_Click`.  
  
     Дополнительные сведения см. в разделе [как: переименовать идентификатор (Visual Basic)](http://msdn.microsoft.com/en-us/e5a5edf8-3dba-4119-81f4-fc2aba180e0c).  
  
9. Вставьте следующий код в `stackButton_Click` обработчика событий.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. В конструкторе Windows Forms выберите `calendarStackButton` элемента управления.  
  
11. В **свойства** задайте событие Click `stackButton_Click` обработчика событий.  
  
12. Повторите шаги 10 и 11 for `contactsStackButton` и `tasksStackButton` элементов управления.  
  
## <a name="defining-icons"></a>Определение значков  
 Каждый `StackView` кнопка имеет значок. Для удобства каждый значок представлен как строка в кодировке Base64, которая десериализуется до <xref:System.Drawing.Bitmap> созданные из нее. В рабочей среде данные точечных рисунков хранятся как ресурс, и значки отображаются в конструкторе Windows Forms. Дополнительные сведения см. в разделе [как: добавление фоновых изображений в Windows Forms](http://msdn.microsoft.com/en-us/7a509ba2-055c-4ae6-b88a-54625c6d9aff).  
  
#### <a name="to-define-icons"></a>Чтобы определить значки  
  
1.  В редакторе кода вставьте следующий код в `StackView` определения класса. Этот код инициализирует точечные рисунки для <xref:System.Windows.Forms.ToolStripButton> значков.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  Добавьте вызов `InitializeImages` метод в `StackView` конструктора класса.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a>Реализация пользовательского средства отрисовки  
 Большинство элементов можно настроить `StackView` управления, реализовав класс, производный от <xref:System.Windows.Forms.ToolStripRenderer> класса. В этой процедуре будет реализовывать <xref:System.Windows.Forms.ToolStripProfessionalRenderer> класс, используемый для настройки захвата и изображения градиентного фона для <xref:System.Windows.Forms.ToolStripButton> элементов управления.  
  
#### <a name="to-implement-a-custom-renderer"></a>Для реализации пользовательского средства отрисовки  
  
1.  Вставьте следующий код в `StackView` управлять определением.  
  
     Это определение для `StackRenderer` класс, переопределяющий <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, и <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> методы для создания настраиваемого внешнего вида.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  В `StackView` конструктор элемента управления, создайте новый экземпляр `StackRenderer` класса и присвойте этот экземпляр `stackStrip` элемента управления <xref:System.Windows.Forms.ToolStrip.Renderer%2A> свойство.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a>Тестирование элемента управления StackView  
 `StackView` Управления является производным от <xref:System.Windows.Forms.UserControl> класса. Таким образом, можно протестировать элемент управления с **контейнере для тестирования пользовательских элементов управления**. Дополнительные сведения см. в разделе [Практическое руководство. Тестирование поведения элемента UserControl во время выполнения](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### <a name="to-test-the-stackview-control"></a>Чтобы протестировать элемент управления StackView  
  
1.  Нажмите клавишу F5, чтобы построить проект и запустить **тестовый контейнер пользовательских элементов управления**.  
  
2.  Переместите указатель над кнопками элемента `StackView` управления, а затем нажмите кнопку для просмотра внешнего вида выбранного состояния.  
  
## <a name="next-steps"></a>Следующие шаги  
 В этом пошаговом руководстве вы создали для повторного использования пользовательский клиентский элемент управления с профессиональный внешний вид элемента управления Office XP. Можно использовать <xref:System.Windows.Forms.ToolStrip> семейства элементов управления для других целей:  
  
-   Создать контекстное меню для элементов управления с <xref:System.Windows.Forms.ContextMenuStrip>. Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Создание формы с автоматически заполняемый стандартным меню. Дополнительные сведения см. в разделе [Пошаговое руководство: создание стандартных пунктов меню к форме](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Создайте форму многодокументного интерфейса (MDI) с закрепление <xref:System.Windows.Forms.ToolStrip> элементов управления. Дополнительные сведения см. в разделе [как: Создание формы MDI ПУТЕМ слияния меню и элементов управления ToolStrip с](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [Практическое руководство. Связывание с формой стандартных элементов меню](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
