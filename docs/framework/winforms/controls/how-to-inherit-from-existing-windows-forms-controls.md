---
title: Наследование от существующих элементов управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d0025ba136698c0a74a73e64a83fa4f526e44843
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736480"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>Практическое руководство. Наследование существующих элементов управления Windows Forms

Чтобы расширить функциональные возможности существующего элемента управления, можно создать элемент управления, производный от существующего элемента управления, путем наследования. При наследовании из существующего элемента управления наследуются все его функциональные возможности и визуальные свойства. Например, если вы создавали элемент управления, наследуемый от <xref:System.Windows.Forms.Button>, новый элемент управления будет выглядеть и работать точно так же, как и стандартный элемент управления <xref:System.Windows.Forms.Button>. После этого вы сможете расширить или изменить функциональность нового элемента управления, реализовав пользовательские методы и свойства. В некоторых элементах управления можно также изменить внешний вид наследуемого элемента управления, переопределив его метод <xref:System.Windows.Forms.Control.OnPaint%2A>.

## <a name="to-create-an-inherited-control"></a>Создание наследуемого элемента управления

1. В Visual Studio создайте новый проект **приложения Windows Forms** .

1. В меню **Проект** выберите команду **Добавить новый элемент**.

    Откроется диалоговое окно **Добавление нового элемента**.

1. В диалоговом окне **Добавление нового элемента** дважды щелкните пункт **Пользовательский элемент управления**.

    В ваш проект будет добавлен новый пользовательский элемент управления.

1. При использовании:

    - Visual Basic в верхней части **Обозреватель решений**щелкните " **отобразить все файлы**". Разверните папку CustomControl1.vb и откройте файл CustomControl1.Designer.vb в редакторе кода.
    - C#Откройте CustomControl1.cs в редакторе кода.

1. Нахождение объявления класса, наследуемого от <xref:System.Windows.Forms.Control>.

1. Измените базовый класс для элемента управления, который нужно использовать для наследования.

     Например, если необходимо наследовать от <xref:System.Windows.Forms.Button>, измените объявление класса следующим образом:

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. Если используется Visual Basic, сохраните и закройте файл CustomControl1.Designer.vb. Откройте файл CustomControl1.vb в редакторе кода.

1. Реализуйте необходимые пользовательские методы или свойства, которые будут входить в ваш элемент управления.

1. Если вы хотите изменить графический внешний вид элемента управления, переопределите метод <xref:System.Windows.Forms.Control.OnPaint%2A>.

    > [!NOTE]
    > Переопределение <xref:System.Windows.Forms.Control.OnPaint%2A> не позволит изменять внешний вид всех элементов управления. Эти элементы управления, которые выполняются в Windows (например, <xref:System.Windows.Forms.TextBox>), никогда не вызывают свой метод <xref:System.Windows.Forms.Control.OnPaint%2A> и, таким образом, никогда не будут использовать пользовательский код. Чтобы узнать, доступен ли метод <xref:System.Windows.Forms.Control.OnPaint%2A>, обратитесь к справочной документации по конкретному элементу управления, который вы хотите изменить. Список всех элементов управления Windows Forms см. в разделе [Элементы управления для использования в формах Windows Forms](controls-to-use-on-windows-forms.md). Если элемент управления не имеет <xref:System.Windows.Forms.Control.OnPaint%2A> указан как метод члена, его внешний вид нельзя изменить, переопределив этот метод. Дополнительные сведения о пользовательском оформлении см. в разделе [Рисование и отрисовка пользовательского элемента управления](custom-control-painting-and-rendering.md).

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

1. Сохраните и проверьте элемент управления.

## <a name="see-also"></a>См. также:

- [Разновидности пользовательских элементов управления](varieties-of-custom-controls.md)
- [Практическое руководство. Наследование класса Control](how-to-inherit-from-the-control-class.md)
- [Практическое руководство. Наследование класса UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Практическое руководство. Создание элементов управления для форм Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Пошаговое руководство. наследование от элемента управления Windows Forms](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
