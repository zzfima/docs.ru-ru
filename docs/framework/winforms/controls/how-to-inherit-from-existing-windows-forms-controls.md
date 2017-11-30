---
title: "Практическое руководство. Наследование существующих элементов управления Windows Forms"
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
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6e6133576d65e95ac42a1680de152d84892e2c5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>Практическое руководство. Наследование существующих элементов управления Windows Forms
Чтобы расширить функциональные возможности существующего элемента управления, можно создать элемент управления, производный от существующего элемента управления, путем наследования. При наследовании из существующего элемента управления наследуются все его функциональные возможности и визуальные свойства. Например, при создании элемента управления, который наследуется от <xref:System.Windows.Forms.Button>, новый элемент управления будет выглядеть и act, так же, как стандартный <xref:System.Windows.Forms.Button> элемента управления. После этого вы сможете расширить или изменить функциональность нового элемента управления, реализовав пользовательские методы и свойства. В некоторых элементах управления можно также изменить внешний вид наследуемого элемента управления путем переопределения его <xref:System.Windows.Forms.Control.OnPaint%2A> метод.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-inherited-control"></a>Создание наследуемого элемента управления  
  
1.  Создайте проект **приложения Windows Forms**.  
  
2.  В меню **Проект** выберите команду **Добавить новый элемент**.  
  
     Откроется диалоговое окно **Добавление нового элемента**.  
  
3.  В диалоговом окне **Добавление нового элемента** дважды щелкните пункт **Пользовательский элемент управления**.  
  
     В ваш проект будет добавлен новый пользовательский элемент управления.  
  
4.  Если используется Visual Basic, в верхней части окна **Обозреватель решений** щелкните параметр **Показать все файлы**. Разверните папку CustomControl1.vb и откройте файл CustomControl1.Designer.vb в редакторе кода.  
  
5.  Если используется C#, откройте в редакторе кода файл CustomControl1.cs.  
  
6.  Найдите объявление класса, который наследуется от <xref:System.Windows.Forms.Control>.  
  
7.  Измените базовый класс для элемента управления, который нужно использовать для наследования.  
  
     Например, если вы хотите наследовать <xref:System.Windows.Forms.Button>, измените объявление класса следующим:  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  Если используется Visual Basic, сохраните и закройте файл CustomControl1.Designer.vb. Откройте файл CustomControl1.vb в редакторе кода.  
  
9. Реализуйте необходимые пользовательские методы или свойства, которые будут входить в ваш элемент управления.  
  
10. Если вы хотите изменить графический интерфейс элемента управления, переопределите <xref:System.Windows.Forms.Control.OnPaint%2A> метод.  
  
    > [!NOTE]
    >  Переопределение <xref:System.Windows.Forms.Control.OnPaint%2A> не позволяют изменять внешний вид всех элементов управления. Элементы управления, оформленные средствами Windows (например, <xref:System.Windows.Forms.TextBox>) никогда не вызывать их <xref:System.Windows.Forms.Control.OnPaint%2A> метода и потому не используйте собственный код. См. в справочной документации по конкретным элементом управления, требуется ли изменить <xref:System.Windows.Forms.Control.OnPaint%2A> метод доступен. Список всех элементов управления Windows Forms см. в разделе [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md). Если элемент управления не имеет <xref:System.Windows.Forms.Control.OnPaint%2A> указана метода-члена, путем переопределения этого метода невозможно изменить его внешний вид. Дополнительные сведения о пользовательском оформлении см. в разделе [Рисование и отрисовка пользовательского элемента управления](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
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
  
## <a name="see-also"></a>См. также  
 [Разновидности пользовательских элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [Практическое руководство. Наследование класса Control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [Практическое руководство. Наследование класса UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [Практическое руководство. Создание элементов управления для форм Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [Пошаговое руководство. Наследование элементов управления форм Windows Forms с помощью Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [Пошаговое руководство. Наследование элементов управления форм Windows Forms с помощью Visual C#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
