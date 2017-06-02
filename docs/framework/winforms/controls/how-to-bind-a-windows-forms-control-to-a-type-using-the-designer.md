---
title: "Практическое руководство. Привязка элемента управления Windows Forms к типу с помощью конструктора | Microsoft Docs"
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
  - "BindingSource - компонент [Windows Forms], привязка к типу"
  - "элементы управления [Windows Forms], привязка к типу"
  - "типы [Windows Forms], привязка элементов управления"
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Привязка элемента управления Windows Forms к типу с помощью конструктора
При создании элементов управления, взаимодействующих с данными, иногда нужно привязать элемент управления к типу, а не к объекту.  Обычно нужно привязать элемент управления к типу на этапе разработки, когда данные недоступны, но все равно нужно, чтобы элементу управления отображали данные из открытого интерфейса типа.  Ниже демонстрируется создания нового <xref:System.Windows.Forms.BindingSource>, связанного с типом, а затем связывание одного из свойств типа со свойством <xref:System.Windows.Forms.TextBox.Text%2A> <xref:System.Windows.Forms.TextBox>.  
  
### Для привязки компонента BindingSource к типу выполните следующие действия.  
  
1.  Создайте проект Windows Forms.  
  
     Дополнительные сведения см. в разделе [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  В представлении **разработки** перетащите компонент <xref:System.Windows.Forms.BindingSource> в форму.  
  
3.  В окне **Свойства** щелкните стрелку для свойства <xref:System.Windows.Forms.BindingSource.DataSource%2A>.  
  
4.  В окне **редактора источника данных** выберите **Добавить новый источник данных проекта**.  
  
5.  На странице **Выбор типа источника данных** выберите **Объект** и нажмите кнопку **Далее**.  
  
6.  Выберите тип для привязки.  
  
    -   Если нужный тип находится в текущем проекте или сборка, содержащая тип, уже добавлена, раскройте узлы, чтобы найти нужный тип, и выберите его.  
  
         \-или\-  
  
    -   Если нужный тип находится в другой сборке, щелкните **Добавить ссылку** и перейдите на вкладку **Проекты**.  Выберите проект, содержащий нужный бизнес\-объект, и нажмите кнопку **ОК**.  Проект будет отображен с списке сборок, поэтому нужный тип можно будет найти, раскрыв соответствующие узлы.  
  
        > [!NOTE]
        >  Если требуется выполнить привязку к типу в структуре или сборке Microsoft, снимите флажок **Скрывать сборки, начинающиеся с Microsoft или System**.  
  
7.  Нажмите кнопку **Далее**, а затем **Готово**.  
  
### Для привязки элемента управления к компоненту BindingSource выполните следующие действия.  
  
1.  Добавьте <xref:System.Windows.Forms.TextBox> в форму.  
  
2.  В окне **Свойства** разверните узел **\(DataBindings\)**.  
  
3.  Щелкните стрелку рядом со свойством <xref:System.Windows.Forms.TextBox.Text%2A>.  
  
4.  В **редакторе типов источников данных** раскройте узел для добавленного ранее <xref:System.Windows.Forms.BindingSource> и выберите свойство связанного типа, которое нужно связать со свойством <xref:System.Windows.Forms.TextBox.Text%2A> <xref:System.Windows.Forms.TextBox>.  
  
## См. также  
 [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Практическое руководство. Связывание элемента управления с типом в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)   
 [Привязка элементов управления к данным в Visual Studio](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md)