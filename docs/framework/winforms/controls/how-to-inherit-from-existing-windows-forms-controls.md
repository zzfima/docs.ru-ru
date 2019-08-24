---
title: Практическое руководство. Наследование существующих элементов управления Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0571bd6b169b94b1626bffb0d0793bbb22a93ba0
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015875"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>Практическое руководство. Наследование существующих элементов управления Windows Forms

Чтобы расширить функциональные возможности существующего элемента управления, можно создать элемент управления, производный от существующего элемента управления, путем наследования. При наследовании из существующего элемента управления наследуются все его функциональные возможности и визуальные свойства. Например, если вы создаете элемент управления, наследуемый <xref:System.Windows.Forms.Button>от, новый элемент управления будет выглядеть и работать точно так же <xref:System.Windows.Forms.Button> , как стандартный элемент управления. После этого вы сможете расширить или изменить функциональность нового элемента управления, реализовав пользовательские методы и свойства. В некоторых элементах управления можно также изменить внешний вид наследуемого элемента управления, переопределив его <xref:System.Windows.Forms.Control.OnPaint%2A> метод.

## <a name="to-create-an-inherited-control"></a>Создание наследуемого элемента управления

1. В Visual Studio создайте новый проект **приложения Windows Forms** .

2. В меню **Проект** выберите команду **Добавить новый элемент**.

     Откроется диалоговое окно **Добавление нового элемента**.

3. В диалоговом окне **Добавление нового элемента** дважды щелкните пункт **Пользовательский элемент управления**.

     В ваш проект будет добавлен новый пользовательский элемент управления.

4. При использовании:

   - Visual Basic в верхней части **Обозреватель решений**щелкните " **отобразить все файлы**". Разверните папку CustomControl1.vb и откройте файл CustomControl1.Designer.vb в редакторе кода.
   - C#Откройте CustomControl1.cs в редакторе кода.

6. Находите объявление класса, который наследует от <xref:System.Windows.Forms.Control>.

7. Измените базовый класс для элемента управления, который нужно использовать для наследования.

     Например, если вы хотите наследовать от <xref:System.Windows.Forms.Button>, измените объявление класса следующим образом:

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

8. Если используется Visual Basic, сохраните и закройте файл CustomControl1.Designer.vb. Откройте файл CustomControl1.vb в редакторе кода.

9. Реализуйте необходимые пользовательские методы или свойства, которые будут входить в ваш элемент управления.

10. Если необходимо изменить графический внешний вид элемента управления, переопределите <xref:System.Windows.Forms.Control.OnPaint%2A> метод.

    > [!NOTE]
    > Переопределение <xref:System.Windows.Forms.Control.OnPaint%2A> не позволит изменять внешний вид всех элементов управления. Эти элементы управления, которые выполняются в Windows (например, <xref:System.Windows.Forms.TextBox>), никогда не вызывают свой <xref:System.Windows.Forms.Control.OnPaint%2A> метод и, таким образом, никогда не будут использовать пользовательский код. Чтобы узнать, доступен ли <xref:System.Windows.Forms.Control.OnPaint%2A> метод, обратитесь к справочной документации по конкретному элементу управления, который вы хотите изменить. Список всех элементов управления Windows Forms см. в разделе [Элементы управления для использования в формах Windows Forms](controls-to-use-on-windows-forms.md). Если элемент управления не <xref:System.Windows.Forms.Control.OnPaint%2A> перечислен как метод-член, невозможно изменить его внешний вид, переопределив этот метод. Дополнительные сведения о пользовательском оформлении см. в разделе [Рисование и отрисовка пользовательского элемента управления](custom-control-painting-and-rendering.md).

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

- [Разновидности пользовательских элементов управления](varieties-of-custom-controls.md)
- [Практическое руководство. Наследование от класса Control](how-to-inherit-from-the-control-class.md)
- [Практическое руководство. Наследование от класса UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Практическое руководство. Создание элементов управления для Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Пошаговое руководство: Наследование от элемента управления Windows Forms](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
