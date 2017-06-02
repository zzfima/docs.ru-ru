---
title: "Практическое руководство. Размещение элементов управления в формах Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Location"
  - "Location.Y"
  - "Location.X"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления [Windows Forms]"
  - "элементы управления [Windows Forms], перемещение"
  - "элементы управления [Windows Forms], размещение"
  - "линии привязки"
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Размещение элементов управления в формах Windows Forms
Чтобы расположить элементы управления, можно использовать конструктор Windows Forms или указать свойство <xref:System.Windows.Forms.Control.Location%2A>.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы разместить элемент управления в рабочем поле конструктора Windows Forms  
  
-   Перетащите элемент управления на соответствующее место с помощью мыши.  
  
    > [!NOTE]
    >  Выберите элемент управления и перемещайте его с помощью клавиш со стрелками для более точного расположения.  Для точного размещения можно использовать *линии привязки*.  Дополнительные сведения см. в разделе [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
### Чтобы разместить элемент управления с помощью окна "Свойства"  
  
1.  Щелкните требуемый элемент управления.  
  
2.  В окне **Свойства** введите значения свойства <xref:System.Windows.Forms.Control.Location%2A>, разделенные запятыми, чтобы разместить элемент управления внутри контейнера.  
  
     Первое число \(X\) определяет расстояние от левой границы контейнера; второе число \(Y\) определяет расстояние от верхней границы контейнера. Расстояние измеряется в пикселях.  
  
    > [!NOTE]
    >  Можно развернуть свойство <xref:System.Windows.Forms.Control.Location%2A>, чтобы ввести значения **X** и **Y** отдельно.\<\+\]  
  
### Чтобы разместить элемент управления программными средствами  
  
1.  Установите свойству <xref:System.Windows.Forms.Control.Location%2A> элемента управления значение <xref:System.Drawing.Point>.  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  Измените значение координаты X элемента управления с помощью подчиненного свойства <xref:System.Windows.Forms.Control.Left%2A>.  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### Чтобы изменить расположение элемента управления программными средствами  
  
1.  Чтобы изменять координату X элемента управления, задайте подчиненное свойство <xref:System.Windows.Forms.Control.Left%2A>.  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  Для одновременного задания значений координат X и Y формы Windows Forms используйте свойство <xref:System.Windows.Forms.Control.Location%2A>.  Чтобы задать положение по каждой координате отдельно, используйте подчиненные свойства <xref:System.Windows.Forms.Control.Left%2A> \(**X**\) и <xref:System.Windows.Forms.Control.Top%2A> \(**Y**\).  Не пытайтесь неявно задать координаты X и Y структуры <xref:System.Drawing.Point>, которая определяет расположение кнопки, потому что эта структура содержит копию координат кнопки.  
  
## См. также  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Расположение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Функциональная классификация элементов управления Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)   
 [How to: Set the Screen Location of Windows Forms](http://msdn.microsoft.com/ru-ru/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)