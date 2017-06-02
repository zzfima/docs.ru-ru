---
title: "Пошаговое руководство. Создание стандартных пунктов меню для формы | Microsoft Docs"
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
  - "пункты меню, стандартные"
  - "StatusStrip - элемент управления [Windows Forms]"
  - "панели инструментов [Windows Forms], пошаговые руководства"
  - "ToolStrip - элемент управления [Windows Forms]"
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Пошаговое руководство. Создание стандартных пунктов меню для формы
Используя элемент управления <xref:System.Windows.Forms.MenuStrip>, можно создать стандартные меню для своих форм.  
  
 В этом пошаговом руководстве демонстрируется использование элемента управления <xref:System.Windows.Forms.MenuStrip> для создания стандартного меню.  Также форма изменяется при выборе элемента меню.  В этом пошаговом руководстве проиллюстрированы следующие задачи:  
  
-   Создание проекта типа Windows Forms  
  
-   создание стандартного меню;  
  
-   Создание элемента управления <xref:System.Windows.Forms.StatusStrip>.  
  
-   управление выбором элементов меню;  
  
 По завершении этой процедуры создается форма, содержащая стандартное меню, в котором отображаются выбранные элементы меню в элементе управления <xref:System.Windows.Forms.StatusStrip>.  
  
 Чтобы скопировать весь текст кода из этой темы, см. раздел [Практическое руководство. Связывание с формой стандартных элементов меню](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Обязательные компоненты  
 Для выполнения этого пошагового руководства потребуется следующее.  
  
-   Разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, на котором установлена [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
## Создание проекта  
 Для начала следует создать проект и подготовить форму.  
  
#### Создание проекта  
  
1.  Создайте проект "Приложение Windows" с названием StandardMenuForm.  
  
     Дополнительные сведения см. в разделе [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  В конструкторе Windows Forms выберите форму.  
  
## Создание стандартного меню  
 Конструктор Windows Forms может автоматически добавить стандартные элементы меню в элемент управления <xref:System.Windows.Forms.MenuStrip>.  
  
#### Чтобы создать стандартное меню  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.MenuStrip> из **панели элементов** в свою форму.  
  
2.  Щелкните для элемента управления <xref:System.Windows.Forms.MenuStrip> глиф смарт\-тега \(![Глиф смарт&#45;тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) и выберите **Вставить стандартные элементы**.  
  
     Элемент управления <xref:System.Windows.Forms.MenuStrip> заполняется стандартными элементами меню.  
  
3.  Щелкните меню **Файл** для просмотра элементов меню по умолчанию и соответствующих им значков.  
  
## Создание элемента управления StatusStrip  
 Используйте элемент управления <xref:System.Windows.Forms.StatusStrip> для отображения состояния приложений Windows Forms.  В этом примере выбранные пользователем элементы меню отображаются в элементе управления <xref:System.Windows.Forms.StatusStrip>.  
  
#### Чтобы создать элемент управления StatusStrip  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.StatusStrip> из **панели элементов** в свою форму.  
  
     Элемент управления <xref:System.Windows.Forms.StatusStrip> автоматически располагается в нижней части формы.  
  
2.  Нажмите кнопку раскрывающегося списка для элемента управления <xref:System.Windows.Forms.StatusStrip> и выберите **StatusLabel** для добавления элемента управления <xref:System.Windows.Forms.ToolStripStatusLabel> в элемент управления <xref:System.Windows.Forms.StatusStrip>.  
  
## Управление выбором элементов  
 Обработайте событие <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>, чтобы оно реагировало на выделение элемента меню пользователем.  
  
#### Чтобы управлять выбором элементов  
  
1.  Выберите пункт меню **Файл**, созданный при создании стандартного раздела меню.  
  
2.  В окне **Свойства** щелкните **События**.  
  
3.  Дважды щелкните событие <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.  
  
     Конструктор Windows Forms генерирует обработчик событий для события <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.  
  
4.  Вставьте следующий код в обработчик события.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  Вставьте в форму определение служебного метода `UpdateStatus`.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## Контрольная точка  
  
#### Чтобы проверить работоспособность формы  
  
1.  Нажмите клавишу F5 чтобы скомпилировать и выполнить полученную форму.  
  
2.  Щелкните элемент меню **Файл**, чтобы открыть меню.  
  
3.  В меню **Файл** выберите один из элементов, щелкнув по нему.  
  
     Элемент управления <xref:System.Windows.Forms.StatusStrip> отображает выбранный элемент.  
  
## Следующие действия  
 В этом пошаговом руководстве была создана форма, содержащая стандартное меню.  Семейством элементов управления <xref:System.Windows.Forms.ToolStrip> можно также пользоваться для многих других целей:  
  
-   Создайте контекстное меню для своих элементов управления с помощью <xref:System.Windows.Forms.ContextMenuStrip>.  Дополнительные сведения см. в разделе [Общие сведения об элементе управления ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Создайте форму многодокументного интерфейса MDI с закрепленными элементами управления <xref:System.Windows.Forms.ToolStrip>.  Дополнительные сведения см. в разделе [Пример. Создание формы MDI путем слияния меню и с применением и элементов управления ToolStrip](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
-   Придайте своим элементам управления <xref:System.Windows.Forms.ToolStrip> профессиональный вид.  Дополнительные сведения см. в разделе [Практическое руководство. Задание средства визуализации компонента ToolStrip для приложения](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## См. также  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [Элемент управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)