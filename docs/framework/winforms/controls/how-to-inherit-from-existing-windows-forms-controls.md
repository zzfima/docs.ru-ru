---
title: "Практическое руководство. Наследование существующих элементов управления Windows Forms | Microsoft Docs"
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
  - "пользовательские элементы управления [Windows Forms], наследование"
  - "наследование, пользовательские элементы управления Windows Forms"
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Наследование существующих элементов управления Windows Forms
Если нужно расширить функции существующего элемента управления, можно путем наследования создать элемент управления, производный от существующего.  При наследовании существующего элемента управления наследуются все его функции и визуальные свойства.  Например, если создан элемент управления, унаследованный из элемента управления <xref:System.Windows.Forms.Button>, новый элемент управления будет выглядеть и действовать так же, как и стандартный элемент управления <xref:System.Windows.Forms.Button>.  Можно затем расширить или изменить функции нового элемента управления, реализовав собственные методы и свойства.  В некоторых элементах управления можно также изменить внешний вид наследуемого элемента управления путем переопределения его метода <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы создать наследуемый элемент управления  
  
1.  Создайте новый проект **Приложение Windows Forms**.  
  
2.  В меню **Проект** выберите **Добавить новый элемент**.  
  
     Открывается диалоговое окно **Добавление нового элемента**.  
  
3.  В диалоговом окне **Добавить новый элемент** дважды щелкните **Настраиваемый элемент управления**.  
  
     В проект добавится новый настраиваемый элемент управления.  
  
4.  При использовании Visual Basic в верхней части **обозревателя решений** щелкните **Показать все файлы**.  Разверните CustomControl1.vb и откройте CustomControl1.Designer.vb в редакторе кода.  
  
5.  При использовании C\# откройте CustomControl1.cs в редакторе кода.  
  
6.  Найдите объявление класса, который наследуется от <xref:System.Windows.Forms.Control>.  
  
7.  Измените базовый класс на элемент управления, из которого необходимо выполнить наследование.  
  
     Например, если нужно наследовать из объекта <xref:System.Windows.Forms.Button>, измените объявление класса следующим образом.  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  При использовании Visual Basic сохраните и закройте CustomControl1.Designer.vb.  Откройте CustomControl1.vb в редакторе кода.  
  
9. Реализуйте необходимые методы или свойства для элемента управления.  
  
10. Если нужно изменить графический интерфейс элемента управления, переопределите метод <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
    > [!NOTE]
    >  Переопределение метода <xref:System.Windows.Forms.Control.OnPaint%2A> позволяет изменять внешний вид не для всех элементов управления.  Элементы управления, оформленные средствами Windows \(например, <xref:System.Windows.Forms.TextBox>\), никогда не вызывают собственный метод <xref:System.Windows.Forms.Control.OnPaint%2A> и потому не используют нестандартный код.  Сведения о доступности метода <xref:System.Windows.Forms.Control.OnPaint%2A> для изменения см. в документации соответствующего элемента управления.  Список всех элементов управления Windows Forms см. в разделе [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).  Если в списке методов элемента управления нет метода <xref:System.Windows.Forms.Control.OnPaint%2A>, то изменение интерфейса путем переопределения этого метода невозможно.  Дополнительные сведения о пользовательском оформлении см. в разделе [Рисование и отрисовка пользовательского элемента управления](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
    ```vb  
    Protected Overrides Sub OnPaint(ByVal e As _  
       System.Windows.Forms.PaintEventArgs)  
       MyBase.OnPaint(e)  
       ' Insert code to do custom painting.   
       ' If you want to completely change the appearance of your control,  
       ' do not call MyBase.OnPaint(e).  
    End Sub  
  
    ```  
  
    ```csharp  
    protected override void OnPaint(PaintEventArgs pe)  
    {  
       base.OnPaint(pe);  
       // Insert code to do custom painting.  
       // If you want to completely change the appearance of your control,  
       // do not call base.OnPaint(pe).  
    }  
    ```  
  
11. Сохраните и проверьте элемент управления.  
  
## См. также  
 [Создание собственных элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [Практическое руководство. Наследование класса Control.](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)   
 [Практическое руководство. Наследование класса UserControl.](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)   
 [Практическое руководство. Создание элементов управления для форм Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)   
 [Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)   
 [Пример. Наследование элементов управления форм Windows Forms с помощью Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)   
 [Пример. Наследование элементов управления форм Windows Forms с помощью Visual C\#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)