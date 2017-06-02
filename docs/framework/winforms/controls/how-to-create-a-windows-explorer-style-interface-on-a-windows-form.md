---
title: "Практическое руководство. Создание интерфейса в стиле проводника в форме Windows Forms | Microsoft Docs"
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
  - "формы, тип проводника Windows"
  - "SplitContainer - элемент управления [Windows Forms], стиль интерфейса проводника"
  - "Проводник Windows, создание с помощью Windows Forms"
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Создание интерфейса в стиле проводника в форме Windows Forms
Пользовательский интерфейс проводника часто используется в приложениях, поскольку он хорошо знаком всем пользователям.  
  
 Проводник — это, по существу, элементы управления <xref:System.Windows.Forms.TreeView> и <xref:System.Windows.Forms.ListView>, расположенные на отдельных панелях.  Размеры панелей можно изменить с помощью разделителя.  Это сочетание элементов управления является весьма эффективным для отображения и просмотра информации.  
  
 В приведенных ниже действиях описано размещение элементов управления в формах, аналогичных проводнику.  В них не описано добавление функций просмотра файлов приложения проводника Windows.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы создать в Windows Forms форму, аналогичную проводнику, выполните следующие действия:  
  
1.  Создайте новый проект "Приложение Windows".  Дополнительные сведения см. в разделе [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  В **панели элементов**:  
  
    1.  Перетащите элемент управления <xref:System.Windows.Forms.SplitContainer> на форму.  
  
    2.  Перетащите элемент управления <xref:System.Windows.Forms.TreeView> в **SplitterPanel1** \(панель элемента управления <xref:System.Windows.Forms.SplitContainer> с пометкой **Panel1**\).  
  
    3.  Перетащите элемент управления <xref:System.Windows.Forms.ListView> в **SplitterPanel2** \(панель элемента управления <xref:System.Windows.Forms.SplitContainer> с пометкой **Panel2**\).  
  
3.  Выберите все три элемента управления, нажав клавишу CTRL и щелкнув последовательно каждый из них.  При выборе элемента управления <xref:System.Windows.Forms.SplitContainer> щелкните разделитель, а не панели.  
  
    > [!NOTE]
    >  Не используйте команду **Выделить все** в меню **Правка**.  Если это сделать, то свойство, необходимое в следующем действии, не появится в окне **Свойства**.  
  
4.  В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.SplitContainer.Dock%2A> значение <xref:System.Windows.Forms.DockStyle>.  
  
5.  Нажмите клавишу F5 для запуска приложения.  
  
     Отображается форма с состоящим из двух частей пользовательским интерфейсом, аналогичным интерфейсу проводника Windows.  
  
    > [!NOTE]
    >  При перетаскивании разделителя размер панелей меняется соответствующим образом.  
  
## См. также  
 <xref:System.Windows.Forms.SplitContainer>   
 [Практическое руководство. Создание пользовательского интерфейса с несколькими областями с помощью Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)   
 [Практическое руководство. Определение способа изменения размеров и позиционирования в окне с перемещаемым разделителем](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)   
 [Практическое руководство. Разделение окна по горизонтали](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)   
 [Элемент управления SplitContainer](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)