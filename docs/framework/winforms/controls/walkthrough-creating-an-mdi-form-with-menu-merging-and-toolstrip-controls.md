---
title: "Пример. Создание формы MDI путем слияния меню и с применением и элементов управления ToolStrip | Microsoft Docs"
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
  - "MDI-формы"
  - "MDI-формы, создание"
  - "MDI-формы, пошаговые руководства"
  - "MDI - интерфейс, создание форм"
  - "формы, основанные на интерфейсе MDI"
  - "панели инструментов [Windows Forms]"
  - "ToolStrip - элемент управления [Windows Forms]"
  - "ToolStripPanel - элемент управления [Windows Forms]"
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Пример. Создание формы MDI путем слияния меню и с применением и элементов управления ToolStrip
Пространство имен <xref:System.Windows.Forms?displayProperty=fullName> поддерживает приложения с многооконным интерфейсом \(MDI\), а элемент управления <xref:System.Windows.Forms.MenuStrip> поддерживает слияние меню.  Формы MDI могут также содержать элементы управления <xref:System.Windows.Forms.ToolStrip>.  
  
 Это пошаговое руководство демонстрирует использование элементов управления <xref:System.Windows.Forms.ToolStripPanel> с формой MDI.  Эта форма также поддерживает слияние меню с вложенными меню.  В этом пошаговом руководстве проиллюстрированы следующие задачи:  
  
-   Создание проекта типа Windows Forms  
  
-   Создание главного меню для формы.  Фактическое имя меню может отличаться.  
  
-   Добавление элемента управления <xref:System.Windows.Forms.ToolStripPanel> на **панель элементов**.  
  
-   Создание дочерней формы.  
  
-   Упорядочивание элементов управления <xref:System.Windows.Forms.ToolStripPanel> в соответствии с z\-порядком.  
  
 Когда выполнение примера будет завершено, получится форма MDI, поддерживающая слияния меню и перемещаемые элементы управления <xref:System.Windows.Forms.ToolStrip>.  
  
 Чтобы скопировать весь текст кода из этой темы, см. ссылку [Практическое руководство. Создание формы MDI путем слияния меню и с применением и элементов управления ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Обязательные компоненты  
 Для выполнения этого пошагового руководства потребуется следующее.  
  
-   Разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, на котором установлена [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
## Создание проекта  
 Для начала следует создать проект и подготовить форму.  
  
#### Создание проекта  
  
1.  Создайте проект "Приложение Windows" с названием MdiForm.  
  
     Дополнительные сведения см. в разделе [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  В конструкторе Windows Forms выберите форму.  
  
3.  В окне "Свойства" установите значение <xref:System.Windows.Forms.Form.IsMdiContainer%2A> на `true`.  
  
## Создание главного меню.  
 Родительская форма MDI содержит главное меню.  В главном меню есть один элемент с названием **Окно**.  С помощью элемента меню **Окно** можно создать дочерние формы.  Элементы меню из дочерних форм сливаются с главным меню.  
  
#### Чтобы создать главное меню  
  
1.  Из **панели элементов** перетащите на форму элемент управления <xref:System.Windows.Forms.MenuStrip>.  
  
2.  Добавьте элемент <xref:System.Windows.Forms.ToolStripMenuItem> в элемент управления <xref:System.Windows.Forms.MenuStrip> и присвойте ему имя "Окно".  
  
3.  Выберите элемент управления <xref:System.Windows.Forms.MenuStrip>.  
  
4.  В окне "Свойства" установите для свойства <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> значение `ToolStripMenuItem1`.  
  
5.  Добавьте подэлемент в элемент меню **Окно** и присвойте этому подэлементу имя "Новый".  
  
6.  В окне "Свойства" нажмите кнопку **События**.  
  
7.  Дважды щелкните событие <xref:System.Windows.Forms.ToolStripItem.Click>.  
  
     Конструктор Windows Forms генерирует обработчик события <xref:System.Windows.Forms.ToolStripItem.Click>.  
  
8.  Вставьте следующий код в обработчик события.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## Добавление элемента управления ToolStripPanel на панель элементов.  
 При использовании элементов управления <xref:System.Windows.Forms.MenuStrip> с формой MDI необходимо наличие элемента управления <xref:System.Windows.Forms.ToolStripPanel>.  Для создания формы MDI в конструкторе Windows Forms необходимо добавить элемент управления <xref:System.Windows.Forms.ToolStripPanel> на **панель элементов**.  
  
#### Добавление элемента управления ToolStripPanel на панель элементов  
  
1.  Откройте **панель элементов** и выберите вкладку **Все формы Windows Forms**, чтобы отобразить доступные элементы управления Windows Forms.  
  
2.  Щелкните правой кнопкой мыши, чтобы открыть контекстное меню, и выберите пункт **Выбрать элементы**.  
  
3.  В диалоговом окне **Выбор элементов панели элементов** прокрутите вниз столбец **Имя**, пока не увидите элемент **ToolStripPanel**.  
  
4.  Установите флажок рядом с элементом **ToolStripPanel** и нажмите кнопку **ОК**.  
  
     Элемент управления <xref:System.Windows.Forms.ToolStripPanel> появится на **панели элементов**.  
  
## Создание дочерней формы.  
 В этой процедуре предстоит определить отдельный класс дочерней формы с собственным элементом управления <xref:System.Windows.Forms.MenuStrip>.  Элементы меню этой формы сливаются с элементами родительской формы.  
  
#### Определение дочерней формы  
  
1.  Добавьте в проект новую форму с именем `ChildForm`.  
  
     Дополнительные сведения см. в разделе [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/ru-ru/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
2.  Из **панели элементов** перетащите на дочернюю форму элемент управления <xref:System.Windows.Forms.MenuStrip>.  
  
3.  Щелкните для элемента управления <xref:System.Windows.Forms.MenuStrip> глиф смарт\-тега \(![Глиф смарт&#45;тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) и выберите пункт **Изменение элементов**.  
  
4.  В диалоговом окне **Редактор коллекции элементов** добавьте новый элемент <xref:System.Windows.Forms.ToolStripMenuItem> с именем ChildMenuItem в дочернее меню.  
  
     Дополнительные сведения см. в разделе [ToolStrip Items Collection Editor](http://msdn.microsoft.com/ru-ru/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).  
  
## Проверка работоспособности полученной формы.  
  
#### Чтобы проверить работоспособность формы  
  
1.  Нажмите клавишу F5 чтобы скомпилировать и выполнить полученную форму.  
  
2.  Выберите элемент меню **Окно**, чтобы открыть меню, и выберите пункт **Новое**.  
  
     В клиентской области MDI формы будет создана новая дочерняя форма.  Меню дочерней формы сливается с главным меню.  
  
3.  Закройте дочернюю форму.  
  
     Меню дочерней формы удаляется из главного меню.  
  
4.  Несколько раз нажмите **Новое**.  
  
     Дочерние формы автоматически перечисляются в пункте меню **Окно**, потому что элементу управления <xref:System.Windows.Forms.MenuStrip> назначается свойство <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>.  
  
## Добавление поддержки элемента управления ToolStrip  
 В этой процедуре в родительскую форму MDI добавляются четыре элемента управления <xref:System.Windows.Forms.ToolStrip>.  Каждый элемент управления <xref:System.Windows.Forms.ToolStrip> добавляется внутри элемента управления <xref:System.Windows.Forms.ToolStripPanel>, который присоединен к краю формы.  
  
#### Чтобы добавить элементы управления ToolStrip в родительскую форму MDI  
  
1.  Из **панели элементов** перетащите на форму элемент управления <xref:System.Windows.Forms.ToolStripPanel>.  
  
2.  Выбрав элемент управления <xref:System.Windows.Forms.ToolStripPanel> дважды щелкните элемент управления <xref:System.Windows.Forms.ToolStrip> на **панели элементов**.  
  
     Элемент управления <xref:System.Windows.Forms.ToolStrip> создается в элементе управления <xref:System.Windows.Forms.ToolStripPanel>.  
  
3.  Выберите элемент управления <xref:System.Windows.Forms.ToolStripPanel>.  
  
4.  В окне "Свойства" измените значение свойства <xref:System.Windows.Forms.Control.Dock%2A> элемента управления на <xref:System.Windows.Forms.DockStyle>.  
  
     Элемент управления <xref:System.Windows.Forms.ToolStripPanel> закрепляется на левой стороне формы под главным меню.  Размер клиентской области MDI изменяется в соответствии с размером элемента управления <xref:System.Windows.Forms.ToolStripPanel>.  
  
5.  Повторите шаги с 1 по 4.  
  
     Закрепите новый элемент управления <xref:System.Windows.Forms.ToolStripPanel> в верхней части формы.  
  
     Элемент управления <xref:System.Windows.Forms.ToolStripPanel> закрепляется под главным меню, но справа от первого элемента управления <xref:System.Windows.Forms.ToolStripPanel>.  Этот этап иллюстрирует важность z\-порядка для правильного расположения элементов управления <xref:System.Windows.Forms.ToolStripPanel>.  
  
6.  Повторите этапы 1 — 4 еще для двух элементов управления <xref:System.Windows.Forms.ToolStripPanel>.  
  
     Закрепите новые элементы управления <xref:System.Windows.Forms.ToolStripPanel> на правой и нижней сторонах формы.  
  
## Упорядочивание элементов управления ToolStripPanel в соответствии с Z\-порядком  
 Положение закрепленного элемента управления <xref:System.Windows.Forms.ToolStripPanel> на форме MDI определяется положением этого элемента управления в z\-порядке.  Задать z\-порядок элементов управления можно удобно в окне "Структура документа".  
  
#### Чтобы упорядочить элементы управления ToolStripPanel в соответствии с Z\-порядком  
  
1.  В меню **Вид** выберите пункт **Другие окна**, а затем пункт **Структура документа**.  
  
     Расположение элементов управления <xref:System.Windows.Forms.ToolStripPanel> в предыдущей процедуре является нестандартным.  Это происходить из\-за неправильного z\-порядка.  Для изменения z\-порядка элементов управления воспользуйтесь окном "Структура документа".  
  
2.  В окне "Структура документа" выберите элемент управления **ToolStripPanel4**.  
  
3.  Нажимайте кнопку со стрелкой вниз до тех пор, пока элемент управления **ToolStripPanel4** не окажется внизу списка.  
  
     Элемент управления **ToolStripPanel4** закрепляется на нижней стороне формы, под другими элементами управления.  
  
4.  Выберите элемент управления **ToolStripPanel2**.  
  
5.  Нажмите кнопку со стрелкой вниз один раз, чтобы сделать этот элемент управления третьим в списке.  
  
     Элемент управления **ToolStripPanel2** закрепляется на верхней стороне формы под главным меню и над другими элементами управления.  
  
6.  Выберите разные элементы управления в окне **Структура документа** и переместите их в разные положения в соответствии с z\-порядком.  Обратите внимание на действие, оказываемое z\-порядком на положение закрепленных элементов управления.  Для отмены сделанных изменений воспользуйтесь комбинацией клавиш CTRL\-Z или командой **Отменить** в меню **Правка**.  
  
## Контрольная точка  
  
#### Чтобы проверить работоспособность формы  
  
1.  Нажмите клавишу F5 чтобы скомпилировать и выполнить полученную форму.  
  
2.  Щелкните захват элемента управления <xref:System.Windows.Forms.ToolStrip> и попробуйте перетащить элемент управления в разные положения на форме.  
  
     Можно перетащить элемент управления <xref:System.Windows.Forms.ToolStrip> с одного элемента управления <xref:System.Windows.Forms.ToolStripPanel> на другой.  
  
## Следующие действия  
 В этом пошаговом руководстве была создана родительская форма MDI с элементами управления <xref:System.Windows.Forms.ToolStrip> и слиянием меню.  Семейством элементов управления <xref:System.Windows.Forms.ToolStrip> можно также пользоваться для многих других целей:  
  
-   Создайте контекстное меню для своих элементов управления с помощью <xref:System.Windows.Forms.ContextMenuStrip>.  Дополнительные сведения см. в разделе [Общие сведения об элементе управления ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Создана форма с автоматически заполняемым стандартным меню.  Дополнительные сведения см. в разделе [Пошаговое руководство. Создание стандартных пунктов меню для формы](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Придайте своим элементам управления <xref:System.Windows.Forms.ToolStrip> профессиональный вид.  Дополнительные сведения см. в разделе [Практическое руководство. Задание средства визуализации компонента ToolStrip для приложения](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## См. также  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [Практическое руководство. Создание родительских MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Практическое руководство. Создание дочерних MDI\-форм](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Практическое руководство. Вставка элемента MenuStrip в раскрывающееся меню интерфейса MDI](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)   
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)