---
title: Пример. Создание формы MDI путем слияния меню и с применением и элементов управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: 124f822aeab25f49cea0ad542497a91a9e2030d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Пример. Создание формы MDI путем слияния меню и с применением и элементов управления ToolStrip
Пространство имен <xref:System.Windows.Forms?displayProperty=nameWithType> поддерживает приложения с интерфейсом MDI, а элемент управления <xref:System.Windows.Forms.MenuStrip> поддерживает слияние меню. Формы MDI также могут содержать элементы управления <xref:System.Windows.Forms.ToolStrip>.  
  
 В этом пошаговом руководстве демонстрируется использование <xref:System.Windows.Forms.ToolStripPanel> элементов управления с формой MDI. Форма также поддерживает слияние меню с вложенными меню. В этом пошаговом руководстве представлены следующие задачи:  
  
-   Создание проекта Windows Forms.  
  
-   Создание главного меню для формы. Фактическое имя меню будет различным.  
  
-   Добавление <xref:System.Windows.Forms.ToolStripPanel> управления **элементов**.  
  
-   Создание дочерней формы.  
  
-   Упорядочение <xref:System.Windows.Forms.ToolStripPanel> элементов управления с z порядком.  
  
 По завершении вы получите формы MDI, также поддерживает слияние меню и доступные <xref:System.Windows.Forms.ToolStrip> элементов управления.  
  
 Скопируйте код из этой темы, в разделе [как: Создание формы MDI ПУТЕМ слияния меню и элементов управления ToolStrip с](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения данного пошагового руководства требуется:  
  
-   Разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, где установлена среда Visual Studio.  
  
## <a name="creating-the-project"></a>Создание проекта  
 Первым шагом является создание проекта и настройка формы.  
  
#### <a name="to-create-the-project"></a>Создание проекта  
  
1.  Создайте проект приложения Windows с именем **MdiForm**.  
  
     Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения WPF](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  В конструкторе Windows Forms выберите форму.  
  
3.  В окне свойств установите для параметра <xref:System.Windows.Forms.Form.IsMdiContainer%2A> для `true`.  
  
## <a name="creating-the-main-menu"></a>Создание главного меню  
 Родительской формы MDI содержит главное меню. В главном меню есть один под названием **окна**. С **окна** пункта меню можно создавать дочерние формы. Элементы меню из дочерних форм сливаются в главном меню.  
  
#### <a name="to-create-the-main-menu"></a>Чтобы создать главное меню  
  
1.  Из **элементов**, перетащите <xref:System.Windows.Forms.MenuStrip> в форму элемент управления.  
  
2.  Добавить <xref:System.Windows.Forms.ToolStripMenuItem> для <xref:System.Windows.Forms.MenuStrip> управления и назовите его **окна**.  
  
3.  Выберите элемент управления <xref:System.Windows.Forms.MenuStrip>.  
  
4.  В окне свойств установите для параметра <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> свойства `ToolStripMenuItem1`.  
  
5.  Добавьте подэлемент для **окна** пункт меню, а затем имя вложенного элемента **New**.  
  
6.  В окне «Свойства» щелкните **события**.  
  
7.  Дважды щелкните <xref:System.Windows.Forms.ToolStripItem.Click> событий.  
  
     Конструктор Windows Forms создает обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> события.  
  
8.  Вставьте следующий код в обработчик событий.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a>Добавление на панель элементов управления ToolStripPanel  
 При использовании <xref:System.Windows.Forms.MenuStrip> элементов управления с формой MDI, необходимо иметь <xref:System.Windows.Forms.ToolStripPanel> элемента управления. Необходимо добавить <xref:System.Windows.Forms.ToolStripPanel> управления **элементов** для создания формы MDI в конструкторе Windows Forms.  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a>Чтобы добавить на панель элементов управления ToolStripPanel  
  
1.  Откройте **элементов**, а затем нажмите кнопку **все формы Windows Forms** вкладку для отображения доступных элементов управления Windows Forms.  
  
2.  Щелкните правой кнопкой мыши, чтобы открыть контекстное меню и выберите **Выбор элементов**.  
  
3.  В **Выбор элементов панели элементов** диалоговое окно, прокрутите вниз **имя** столбца, пока не найдете **ToolStripPanel**.  
  
4.  Установите флажок рядом с **ToolStripPanel**, а затем нажмите кнопку **ОК**.  
  
     <xref:System.Windows.Forms.ToolStripPanel> Элемент управления отображается в **элементов**.  
  
## <a name="creating-a-child-form"></a>Создание дочерней формы  
 В этой процедуре мы определим отдельный класс дочерней формы с собственным <xref:System.Windows.Forms.MenuStrip> элемента управления. Пункты меню для этой формы, объединяются с разрешениями родительской формы.  
  
#### <a name="to-define-a-child-form"></a>Для определения дочерней формы  
  
1.  Добавьте новую форму с именем `ChildForm` в проект.  
  
     Дополнительные сведения см. в разделе [как: добавить Windows Forms в проект](http://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
2.  Из **элементов**, перетащите <xref:System.Windows.Forms.MenuStrip> в форму дочерний элемент управления.  
  
3.  Нажмите кнопку <xref:System.Windows.Forms.MenuStrip> глиф смарт-тега элемента управления (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), а затем выберите **изменение элементов**.  
  
4.  В **редактор коллекции элементов** диалогового окна поле, добавьте новый <xref:System.Windows.Forms.ToolStripMenuItem> с именем **ChildMenuItem** в дочерних меню.  
  
     Дополнительные сведения см. в разделе [редактор коллекции элементов ToolStrip](http://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).  
  
## <a name="testing-the-form"></a>Тестирование формы  
  
#### <a name="to-test-your-form"></a>Чтобы проверить работоспособность формы  
  
1.  Нажмите клавишу F5, чтобы скомпилировать и запустить форму.  
  
2.  Нажмите кнопку **окна** пункт меню, чтобы открыть меню и нажмите кнопку **New**.  
  
     В клиентской области формы MDI создается новый дочерней формы. Меню дочерней формы сливается с главным меню.  
  
3.  Закройте дочерней формы.  
  
     Меню дочерней формы удаляется из главного меню.  
  
4.  Нажмите кнопку **New** несколько раз.  
  
     Дочерние формы автоматически перечисляются в W**окно** меню элемента, так как <xref:System.Windows.Forms.MenuStrip> элемента управления <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> присваивается.  
  
## <a name="adding-toolstrip-support"></a>Добавление поддержки элемента управления ToolStrip  
 В этой процедуре вы добавите четыре <xref:System.Windows.Forms.ToolStrip> элементы управления для родительской MDI-формы. Каждый <xref:System.Windows.Forms.ToolStrip> добавляется элемент управления внутри <xref:System.Windows.Forms.ToolStripPanel> элемента управления, который прикрепляется к края формы.  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a>Добавление элементов управления ToolStrip в родительской MDI-формы  
  
1.  Из **элементов**, перетащите <xref:System.Windows.Forms.ToolStripPanel> в форму элемент управления.  
  
2.  С <xref:System.Windows.Forms.ToolStripPanel> выбран элемент управления, дважды щелкните <xref:System.Windows.Forms.ToolStrip> управления **элементов**.  
  
     Объект <xref:System.Windows.Forms.ToolStrip> создается элемент управления в <xref:System.Windows.Forms.ToolStripPanel> элемента управления.  
  
3.  Выберите элемент управления <xref:System.Windows.Forms.ToolStripPanel>.  
  
4.  В окне «Свойства» измените значение элемента управления <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Left>.  
  
     <xref:System.Windows.Forms.ToolStripPanel> Управления фиксирует элемент управления у левого края формы под главным меню. Изменяет размер клиентской области MDI <xref:System.Windows.Forms.ToolStripPanel> элемента управления.  
  
5.  Повторите шаги 1 – 4.  
  
     Закрепите новые <xref:System.Windows.Forms.ToolStripPanel> элемента управления в верхней части формы.  
  
     <xref:System.Windows.Forms.ToolStripPanel> Управления закрепляется под главным меню, но справа от первой <xref:System.Windows.Forms.ToolStripPanel> элемента управления. В этом разделе рассмотрены важность z порядка правильно расположить <xref:System.Windows.Forms.ToolStripPanel> элементов управления.  
  
6.  Повторите шаги 1 – 4 для еще двух <xref:System.Windows.Forms.ToolStripPanel> элементов управления.  
  
     Закрепите новые <xref:System.Windows.Forms.ToolStripPanel> элементы управления справа и нижней части формы.  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a>Упорядочивание элементов управления ToolStripPanel в соответствии с Z-порядком  
 Положение закрепленного <xref:System.Windows.Forms.ToolStripPanel> элемент управления в форме MDI определяется положение элемента управления в z порядке. Вы можете легко упорядочить z порядок элементов управления в окне «Структура документа».  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a>Размещение элементов управления ToolStripPanel в соответствии с Z-порядком  
  
1.  В **представление** меню, нажмите кнопку **другие окна**, а затем нажмите кнопку **Структура документа**.  
  
     Расположение вашей <xref:System.Windows.Forms.ToolStripPanel> нестандартные элементы управления из предыдущей процедуры. Это так, как неправильный z порядка. Окно Структура документа используется для изменения z порядка элементов управления.  
  
2.  В окне «Структура документа» выберите **ToolStripPanel4**.  
  
3.  Нажмите кнопку со стрелкой вниз, пока **ToolStripPanel4** — в нижней части списка.  
  
     **ToolStripPanel4** управления прикрепляется к нижней части формы, под другими элементами управления.  
  
4.  Выберите **ToolStripPanel2**.  
  
5.  Нажмите кнопку со стрелкой вниз один раз для размещения элемента управления в-третьих, в списке.  
  
     **ToolStripPanel2** управления прикрепляется к верхней части формы под главным меню и над другими элементами управления.  
  
6.  Выберите различные элементы управления в **Структура документа** окна и переместите их в разных местах в z порядке. Пронаблюдайте z-порядок размещения пристыкованных элементов управления. Нажмите CTRL-z или **отменить** на **изменить** меню, чтобы отменить внесенные изменения.  
  
## <a name="checkpoint"></a>Контрольная точка  
  
#### <a name="to-test-your-form"></a>Чтобы проверить работоспособность формы  
  
1.  Нажмите клавишу F5, чтобы скомпилировать и запустить форму.  
  
2.  Щелкните захват элемента <xref:System.Windows.Forms.ToolStrip> управления и перетащите элемент управления в разных местах формы.  
  
     Можно перетащить <xref:System.Windows.Forms.ToolStrip> управления от одного <xref:System.Windows.Forms.ToolStripPanel> элемента управления в другой.  
  
## <a name="next-steps"></a>Следующие шаги  
 В этом пошаговом руководстве вы создали родительской формы MDI с <xref:System.Windows.Forms.ToolStrip> элементов управления и слияние меню. Можно использовать <xref:System.Windows.Forms.ToolStrip> семейства элементов управления для других целей:  
  
-   Создать контекстное меню для элементов управления с <xref:System.Windows.Forms.ContextMenuStrip>. Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Создана форма с автоматически заполняемый стандартным меню. Дополнительные сведения см. в разделе [Пошаговое руководство: создание стандартных пунктов меню к форме](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Предоставьте вашей <xref:System.Windows.Forms.ToolStrip> управляет профессиональный вид. Дополнительные сведения см. в разделе [как: задать средство отрисовки элемента управления ToolStrip для приложения](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [Практическое руководство. Создание родительских MDI-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Практическое руководство. Создание дочерних MDI-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Практическое руководство. Вставка элемента MenuStrip в раскрывающееся меню интерфейса MDI](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
