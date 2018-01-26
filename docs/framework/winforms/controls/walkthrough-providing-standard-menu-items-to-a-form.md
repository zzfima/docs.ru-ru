---
title: "Пошаговое руководство. Создание стандартных пунктов меню для формы"
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
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89089617a62ab079dd4cccf3ddf6e1e774bac8ba
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>Пошаговое руководство. Создание стандартных пунктов меню для формы
С помощью элемента управления <xref:System.Windows.Forms.MenuStrip> можно создавать стандартные меню для форм.  
  
 В этом пошаговом руководстве демонстрируется использование <xref:System.Windows.Forms.MenuStrip> управления создавать стандартные меню. Также форма изменяется, когда пользователь выбирает пункт меню. В этом пошаговом руководстве представлены следующие задачи:  
  
-   Создание проекта Windows Forms.  
  
-   Создание стандартного меню.  
  
-   Создание <xref:System.Windows.Forms.StatusStrip> элемента управления.  
  
-   Управление выбором элементов меню.  
  
 По завершении вы получите формы, содержащей стандартное меню, в котором отображаются выбранные элементы меню в <xref:System.Windows.Forms.StatusStrip> элемента управления.  
  
 Скопируйте код из этой темы, в разделе [как: предоставляют стандартных пунктов меню для формы](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения данного пошагового руководства требуется:  
  
-   Разрешения, достаточные для создания и выполнения проектов приложений Windows Forms на компьютере, где [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] установлен.  
  
## <a name="creating-the-project"></a>Создание проекта  
 Первым шагом является создание проекта и настройка формы.  
  
#### <a name="to-create-the-project"></a>Создание проекта  
  
1.  Создайте проект приложения Windows с именем **StandardMenuForm**.  
  
     Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения WPF](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  В конструкторе Windows Forms выберите форму.  
  
## <a name="creating-a-standard-menu"></a>Создание стандартного меню  
 Конструктор Windows Forms может автоматически заполнять <xref:System.Windows.Forms.MenuStrip> элемента управления с помощью стандартных элементов меню.  
  
#### <a name="to-create-a-standard-menu"></a>Создание стандартного меню  
  
1.  Из **элементов**, перетащите <xref:System.Windows.Forms.MenuStrip> управления на форму.  
  
2.  Нажмите кнопку <xref:System.Windows.Forms.MenuStrip> глиф смарт-тега элемента управления (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) и выберите **вставить стандартные элементы**.  
  
     <xref:System.Windows.Forms.MenuStrip> Управления заполняется стандартных элементов меню.  
  
3.  Нажмите кнопку **файл** элемента меню, чтобы увидеть его элементы меню по умолчанию и соответствующие значки.  
  
## <a name="creating-a-statusstrip-control"></a>Создание элемента управления StatusStrip  
 Используйте <xref:System.Windows.Forms.StatusStrip> элемента управления для отображения состояния для приложений Windows Forms. В этом примере отображаются элементы меню, выбранный пользователем в <xref:System.Windows.Forms.StatusStrip> элемента управления.  
  
#### <a name="to-create-a-statusstrip-control"></a>Создание элемента управления StatusStrip  
  
1.  Из **элементов**, перетащите <xref:System.Windows.Forms.StatusStrip> управления на форму.  
  
     <xref:System.Windows.Forms.StatusStrip> Автоматически прикреплен к нижней части формы.  
  
2.  Нажмите кнопку <xref:System.Windows.Forms.StatusStrip> разворачивающуюся кнопку элемента управления и выберите **StatusLabel** добавление <xref:System.Windows.Forms.ToolStripStatusLabel> управления <xref:System.Windows.Forms.StatusStrip> управления.  
  
## <a name="handling-item-selection"></a>Управление выбором элементов  
 Обрабатывать <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> событий, чтобы ответить, когда пользователь выбирает пункт меню.  
  
#### <a name="to-handle-item-selection"></a>Чтобы управлять выбором элементов  
  
1.  Нажмите кнопку **файл** пункт меню, который был создан при создании стандартного раздела меню.  
  
2.  В **свойства** окно, нажмите кнопку **события**.  
  
3.  Дважды щелкните <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> событий.  
  
     Конструктор Windows Forms создает обработчик событий для <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> события.  
  
4.  Вставьте следующий код в обработчик событий.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  Вставить `UpdateStatus` программа определение метода в форму.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a>Контрольная точка  
  
#### <a name="to-test-your-form"></a>Чтобы проверить работоспособность формы  
  
1.  Нажмите клавишу F5, чтобы скомпилировать и запустить форму.  
  
2.  Нажмите кнопку **файл** пункт меню, чтобы открыть меню.  
  
3.  На **файл** меню, выберите один из элементов, чтобы выбрать его.  
  
     <xref:System.Windows.Forms.StatusStrip> Элемент управления отображает выбранный элемент.  
  
## <a name="next-steps"></a>Следующие шаги  
 В этом пошаговом руководстве вы создали формы, содержащей стандартное меню. Можно использовать <xref:System.Windows.Forms.ToolStrip> семейства элементов управления для других целей:  
  
-   Создать контекстное меню для элементов управления с <xref:System.Windows.Forms.ContextMenuStrip>. Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Создайте форму многодокументного интерфейса (MDI) с закрепление <xref:System.Windows.Forms.ToolStrip> элементов управления. Дополнительные сведения см. в разделе [Пошаговое руководство: Создание формы MDI ПУТЕМ слияния меню и элементов управления ToolStrip с](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
-   Предоставьте вашей <xref:System.Windows.Forms.ToolStrip> управляет профессиональный вид. Дополнительные сведения см. в разделе [как: задать средство отрисовки элемента управления ToolStrip для приложения](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [Элемент управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
