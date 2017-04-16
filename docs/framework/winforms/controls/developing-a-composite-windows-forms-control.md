---
title: "Разработка составного элемента Windows Forms | Microsoft Docs"
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
  - "составные элементы управления"
  - "составные элементы управления, Windows Forms"
  - "элементы управления [Windows Forms], составной"
  - "пользовательские элементы управления [Windows Forms], составные элементы управления"
  - "UserControl - класс"
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Разработка составного элемента Windows Forms
Можно разработать составной элемент управления Windows Forms, объединив другие элементы управления Windows Forms.  Составные элементы управления, которые являются производными от элемента управления [System.Windows.Forms.UserControl](frlrfSystemWebUIUserControlClassTopic), называются пользовательскими элементами управления.  Базовый класс <xref:System.Windows.Forms.UserControl> обеспечивает маршрутизацию событий клавиатуры для дочерних элементов управления, это гарантирует, что дочерние элементы управления смогут получать фокус ввода.  Пример <xref:System.Windows.Forms.UserControl> демонстрирует образец пользовательского элемента управления в разделе [Практическое руководство. Применение атрибутов к элементам управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).  
  
 Конструктор Windows Forms в [!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)] предоставляет широкие возможности поддержки для пользовательских элементов управления во время разработки.  
  
-   [Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))  
  
-   [Пример. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))  
  
-   [Пример. Наследование элементов управления форм Windows Forms с помощью Visual C\#](http://msdn.microsoft.com/ru-ru/library/5h0k2e6x\(v=vs.110\))  
  
-   [Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))  
  
-   [Практическое руководство. Наследование существующих элементов управления Windows Forms](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))  
  
-   [Пример. Отладка пользовательских элементов управления Windows Forms во время разработки](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))  
  
-   [Практическое руководство. Наследование класса Control](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))  
  
-   [Практическое руководство. Тестирование поведения элемента UserControl во время выполнения](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))  
  
-   [Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))  
  
-   [Практическое руководство. Наследование класса UserControl](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))  
  
-   [Практическое руководство. Создание элементов управления для форм Windows Forms](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))  
  
-   [Практическое руководство. Создание составных элементов управления](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))  
  
-   [Пример. Создание составного элемента управления с помощью Visual Basic](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))  
  
-   [Пример. Создание составного элемента управления с помощью Visual  C\#](http://msdn.microsoft.com/ru-ru/library/a6h7e207\(v=vs.110\))  
  
-   [Пример. Наследование элементов управления форм Windows Forms с помощью Visual Basic](http://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))  
  
-   [Практическое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций, применяемых во время разработки](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))  
  
-   [Практическое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций, применяемых во время разработки](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))  
  
## См. также  
 [Практическое руководство. Применение атрибутов к элементам управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)   
 [Разработка пользовательских элементов управления Windows Forms в .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Создание собственных элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)