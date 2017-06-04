---
title: "Пример. Создание профессионально оформленного элемента управления ToolStrip | Microsoft Docs"
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
  - "панели инструментов [Windows Forms], пошаговые руководства"
  - "ToolStrip - элемент управления [Windows Forms], создание профессионально оформленных элементов управления"
  - "ToolStripProfessionalRenderer - класс [Windows Forms]"
  - "ToolStripRenderer - класс [Windows Forms]"
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Пример. Создание профессионально оформленного элемента управления ToolStrip
Чтобы придать элементам управления приложения <xref:System.Windows.Forms.ToolStrip> профессиональный внешний вид и поведение, создайте собственный класс на основе типа <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.  
  
 В этом пошаговом руководстве демонстрируется использование элементов управления <xref:System.Windows.Forms.ToolStrip> для создания составного элемента управления, напоминающего **Область переходов** в Microsoft® Outlook®.  В этом пошаговом руководстве проиллюстрированы следующие задачи:  
  
-   Создание проекта "Библиотека элементов управления Windows"  
  
-   Разработка элемента управления StackView  
  
-   Реализация настраиваемого средства визуализации  
  
 По завершении работы с этим примером создается пользовательский клиентский элемент управления, доступный для многократного использования, имеющий профессиональный внешний вид элемента управления Microsoft Office® XP.  
  
 Чтобы скопировать весь текст кода из этой темы, см. раздел [Практическое руководство. Создание профессионально оформленного элемента управления ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Обязательные компоненты  
 Для выполнения этого пошагового руководства потребуется следующее.  
  
-   Разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, на котором установлена [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
## Создание проекта "Библиотека элементов управления Windows"  
 На первом этапе необходимо создать проект библиотеки элементов управления.  
  
#### Создание проекта библиотеки элементов управления  
  
1.  Создайте новый проект библиотеки элементов управления Windows под названием `StackViewLibrary`.  
  
2.  В **обозревателе решений** удалите элемент управления по умолчанию для этого проекта, удалив исходный файл "UserControl1.cs" или "UserControl1.vb" в зависимости от выбранного языка.  
  
     Дополнительные сведения см. в разделе [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/ru-ru/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
3.  Добавьте новый элемент <xref:System.Windows.Forms.UserControl> в проект **StackViewLibrary**.  Назовите новый исходный файл `StackView`.  
  
## Разработка элемента управления StackView  
 Элемент управления `StackView` – это составной элемент управления, содержащий один дочерний элемент управления <xref:System.Windows.Forms.ToolStrip>.  Дополнительные сведения о составных элементах управления см. в разделе [Создание собственных элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).  
  
#### Чтобы разработать элемент управления StackView  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.ToolStrip> из **панели элементов** на поверхность разработки.  
  
2.  В окне **Свойства** задайте свойства элемента управления <xref:System.Windows.Forms.ToolStrip> в соответствии со следующей таблицей.  
  
    |Свойство.|Значение|  
    |---------------|--------------|  
    |Имя|`stackStrip`|  
    |CanOverflow|`false`|  
    |Dock|<xref:System.Windows.Forms.DockStyle>|  
    |Шрифт|`Tahoma, 10pt, style=Bold`|  
    |GripStyle|<xref:System.Windows.Forms.ToolStripGripStyle>|  
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle>|  
    |Заполнение|`0, 7, 0, 0`|  
    |RenderMode|<xref:System.Windows.Forms.ToolStripRenderMode>|  
  
3.  В конструкторе Windows Forms щелкните кнопку **Добавить** для элемента управления <xref:System.Windows.Forms.ToolStrip> и добавьте <xref:System.Windows.Forms.ToolStripButton> к элементу управления `stackStrip`.  
  
4.  В окне **Свойства** задайте свойства элемента управления <xref:System.Windows.Forms.ToolStripButton> в соответствии со следующей таблицей.  
  
    |Свойство.|Значение|  
    |---------------|--------------|  
    |Имя|`mailStackButton`|  
    |CheckOnClick|true|  
    |CheckState|<xref:System.Windows.Forms.CheckState>|  
    |DisplayStyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle>|  
    |ImageAlign|<xref:System.Drawing.ContentAlignment>|  
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling>|  
    |ImageTransparentColor|`238, 238, 238`|  
    |Margin|`0, 0, 0, 0`|  
    |Заполнение|`3, 3, 3, 3`|  
    |Текст|Почта|  
    |TextAlign|<xref:System.Drawing.ContentAlignment>|  
  
5.  Повторите шаг 7 для еще трех элементов управления <xref:System.Windows.Forms.ToolStripButton>.  
  
     Назовите элементы управления `calendarStackButton`, `contactsStackButton` и `tasksStackButton`.  Укажите для свойства <xref:System.Windows.Forms.Control.Text%2A> значения Calendar, Contacts и Tasks соответственно.  
  
## Обработка событий  
 Для обеспечения корректного поведения элемента управления `StackView` важны два события.  Обработайте событие <xref:System.Windows.Forms.UserControl.Load> для правильного размещения элемента управления.  Обработайте событие <xref:System.Windows.Forms.ToolStripItem.Click> для каждой кнопки <xref:System.Windows.Forms.ToolStripButton>, чтобы поведение состояния элемента управления `StackView` стало похожим на элемент управления <xref:System.Windows.Forms.RadioButton>.  
  
#### Чтобы обработать события  
  
1.  В конструкторе Windows Forms выберите элемент управления `StackView`.  
  
2.  В окне **Свойства** щелкните **События**.  
  
3.  Дважды щелкните событие "Load" для создания обработчика события `StackView_Load`.  
  
4.  В обработчике события `StackView_Load` скопируйте и вставьте следующий код.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  В конструкторе Windows Forms выберите элемент управления `mailStackButton`.  
  
6.  В окне **Свойства** щелкните **События**.  
  
7.  Дважды щелкните событие Click.  
  
     Конструктор Windows Forms генерирует обработчик события для события `mailStackButton_Click`.  
  
8.  Измените имя обработчика события `mailStackButton_Click` на `stackButton_Click`.  
  
     Дополнительные сведения см. в разделе [How to: Rename an Identifier \(Visual Basic\)](http://msdn.microsoft.com/ru-ru/e5a5edf8-3dba-4119-81f4-fc2aba180e0c).  
  
9. Вставьте следующий код в обработчик событий `stackButton_Click`.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. В конструкторе Windows Forms выберите элемент управления `calendarStackButton`.  
  
11. В окне **Свойства** задайте для события Click обработчик событий `stackButton_Click`.  
  
12. Повторите шаги 10 и 11 для элементов управления `contactsStackButton` и `tasksStackButton`.  
  
## Определение значков  
 Каждой кнопке `StackView` назначается определенный значок.  Для удобства каждый значок представлен как строка в кодировке Base64, которая десериализуется до создания <xref:System.Drawing.Bitmap> на ее основе.  В производственной среде данные точечных рисунков хранятся как ресурс, и значки отображаются в конструкторе Windows Forms.  Дополнительные сведения см. в разделе [How to: Add Background Images to Windows Forms](http://msdn.microsoft.com/ru-ru/7a509ba2-055c-4ae6-b88a-54625c6d9aff).  
  
#### Чтобы определить значки  
  
1.  В редакторе кода вставьте следующий код в определение класса `StackView`.  Этот код инициализирует точечные рисунки для значков <xref:System.Windows.Forms.ToolStripButton>.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  Добавьте вызов метода `InitializeImages` в конструктор класса `StackView`.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## Реализация настраиваемого средства визуализации  
 Большую часть элементов элемента управления `StackView` можно настроить, реализовав класс на основе класса <xref:System.Windows.Forms.ToolStripRenderer>.  В этой процедуре необходимо реализовать класс <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, используемый для настройки захвата и изображения градиентного фона для элементов управления <xref:System.Windows.Forms.ToolStripButton>.  
  
#### Чтобы реализовать настраиваемое средство визуализации  
  
1.  Вставьте следующий код в определение элемента управления `StackView`.  
  
     Это определение для класса `StackRenderer`, который переопределяет методы <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder> и <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> для создания настраиваемого внешнего вида.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  В конструкторе элемента управления `StackView` создайте новый экземпляр класса `StackRenderer` и назначьте этот экземпляр свойству <xref:System.Windows.Forms.ToolStrip.Renderer%2A> элемента управления `stackStrip`.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## Тестирование элемента управления StackView  
 Элемент управления `StackView` является производным от класса <xref:System.Windows.Forms.UserControl>.  Следовательно, этот элемент управления можно тестировать с использованием **Тестового контейнера пользовательских элементов управления**.  Дополнительные сведения см. в разделе [Практическое руководство. Тестирование поведения элемента UserControl во время выполнения](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### Чтобы протестировать элемент управления StackView  
  
1.  Нажмите клавишу F5 для построения проекта и запуска **Тестового контейнера пользовательских элементов управления**.  
  
2.  Поместите указатель мыши над кнопками элемента управления `StackView`, а затем щелкните кнопку для просмотра внешнего вида выбранного для нее состояния.  
  
## Следующие действия  
 В этом пошаговом руководстве был создан пользовательский клиентский элемент управления, допускающий многократное использование и имеющий профессиональный внешний вид элемента управления Office XP.  Семейством элементов управления <xref:System.Windows.Forms.ToolStrip> можно также пользоваться для многих других целей:  
  
-   Создайте контекстное меню для своих элементов управления с помощью <xref:System.Windows.Forms.ContextMenuStrip>.  Дополнительные сведения см. в разделе [Общие сведения об элементе управления ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Создайте форму с автоматически заполняемым стандартным меню.  Дополнительные сведения см. в разделе [Пошаговое руководство. Создание стандартных пунктов меню для формы](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Создайте форму многодокументного интерфейса MDI с закрепленными элементами управления <xref:System.Windows.Forms.ToolStrip>.  Дополнительные сведения см. в разделе [Практическое руководство. Создание формы MDI путем слияния меню и с применением и элементов управления ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
## См. также  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)   
 [Практическое руководство. Связывание с формой стандартных элементов меню](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)