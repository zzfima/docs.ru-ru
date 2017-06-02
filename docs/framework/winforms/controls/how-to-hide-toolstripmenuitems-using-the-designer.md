---
title: "Практическое руководство. Скрытие объектов ToolStripMenuItem с помощью конструктора | Microsoft Docs"
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
  - "пункты меню, скрытие"
  - "MenuStrip - элемент управления [Windows Forms], скрытие элементов меню в конструкторе"
  - "ToolStripMenuItem - элементы, скрытие элементов меню в конструкторе"
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Скрытие объектов ToolStripMenuItem с помощью конструктора
Скрытие пунктов меню позволяет управлять пользовательским интерфейсом приложения и ограничивать использование команд пользователями.  Во многих случаях, когда все пункты меню становятся недоступными, необходимо скрыть меню целиком.  Это позволит пользователю меньше отвлекаться.  Более того, можно одновременно скрыть и отключить меню или пункт меню, поскольку скрытие меню не запрещает доступ пользователя к командам меню с помощью сочетаний клавиш.  Дополнительные сведения об отключении пунктов меню см. в разделе [Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы скрыть меню верхнего уровня и его вложенные меню, выполните следующие действия.  
  
1.  Выберите пункт меню верхнего уровня и установите для его свойства <xref:System.Windows.Forms.ToolStripItem.Visible%2A> или <xref:System.Windows.Forms.ToolStripItem.Available%2A> значение `false`.  
  
     При скрытии пункта меню верхнего уровня все пункты меню внутри этого меню также будут скрыты.  Если после присвоения свойству <xref:System.Windows.Forms.ToolStripItem.Visible%2A> значения `false` щелкнуть в любом месте за пределами элемента управления <xref:System.Windows.Forms.MenuStrip>, пункт меню верхнего уровня и его вложенные элементы исчезнут из формы, наглядно продемонстрировав результат этого действия.  Чтобы отобразить скрытое меню верхнего уровня в процессе разработки, щелкните элемент <xref:System.Windows.Forms.MenuStrip> в **области компонентов**, в окне **Структура документа** или в верхней части сетки свойств.  
  
> [!NOTE]
>  Скрытие всего меню полностью выполняется нечасто, за исключением дочерних меню интерфейса MDI в сценарии слияния.  
  
### Чтобы скрыть элемент вложенного меню, выполните следующие действия:  
  
1.  Выберите элемент вложенного меню и установите для его свойства <xref:System.Windows.Forms.ToolStripItem.Visible%2A> значение `false`.  
  
     При скрытии элемента вложенного меню он остается видимым в форме в процессе разработки, что позволяет в дальнейшем легко его выбрать.  Он будет скрыт во время выполнения.  
  
## См. также  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>   
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>   
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>   
 [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)   
 [Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)