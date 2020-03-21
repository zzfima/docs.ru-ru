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
ms.openlocfilehash: b0e0053816efde349c7e4d13d03bef5f8801c667
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849384"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>Практическое руководство. Наследование существующих элементов управления Windows Forms

Чтобы расширить функциональные возможности существующего элемента управления, можно создать элемент управления, производный от существующего элемента управления, путем наследования. При наследовании из существующего элемента управления наследуются все его функциональные возможности и визуальные свойства. Например, если вы создаете элемент <xref:System.Windows.Forms.Button>управления, который унаследовал от, ваш <xref:System.Windows.Forms.Button> новый элемент управления будет выглядеть и действовать точно так же, как стандартный элемент управления. После этого вы сможете расширить или изменить функциональность нового элемента управления, реализовав пользовательские методы и свойства. В некоторых элементах управления вы также можете изменить внешний <xref:System.Windows.Forms.Control.OnPaint%2A> вид унаследованного элемента управления, переопределив его метод.

## <a name="to-create-an-inherited-control"></a>Создание наследуемого элемента управления

1. В Visual Studio создайте новый проект **приложения Windows Forms.**

1. В меню **Проект** выберите команду **Добавить новый элемент**.

    Откроется диалоговое окно **Добавление нового элемента**.

1. В диалоговом окне **Добавление нового элемента** дважды щелкните пункт **Пользовательский элемент управления**.

    В ваш проект будет добавлен новый пользовательский элемент управления.

1. Если вы используете:

    - Визуальный основной, в верхней части **решения Explorer**, нажмите Показать **все файлы**. Разверните папку CustomControl1.vb и откройте файл CustomControl1.Designer.vb в редакторе кода.
    - С CustomControl1.cs.

1. Найдите классную декларацию, <xref:System.Windows.Forms.Control>которая наследует ся.

1. Измените базовый класс для элемента управления, который нужно использовать для наследования.

     Например, если вы хотите <xref:System.Windows.Forms.Button>унаследовать от, измените декларацию класса на следующее:

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. Если используется Visual Basic, сохраните и закройте файл CustomControl1.Designer.vb. Откройте файл CustomControl1.vb в редакторе кода.

1. Реализуйте необходимые пользовательские методы или свойства, которые будут входить в ваш элемент управления.

1. Если вы хотите изменить графический внешний вид <xref:System.Windows.Forms.Control.OnPaint%2A> элемента управления, переопределить метод.

    > [!NOTE]
    > Переопределение <xref:System.Windows.Forms.Control.OnPaint%2A> не позволит вам изменить внешний вид всех элементов управления. Те элементы управления, которые имеют все свои <xref:System.Windows.Forms.TextBox>картины, <xref:System.Windows.Forms.Control.OnPaint%2A> сделанные Windows (например, ) никогда не называют их метод, и, таким образом, никогда не будет использовать пользовательский код. Обратитесь к документации справки для конкретного элемента управления, который вы хотите изменить, чтобы увидеть, доступен ли <xref:System.Windows.Forms.Control.OnPaint%2A> метод. Список всех элементов управления Windows Forms см. в разделе [Элементы управления для использования в формах Windows Forms](controls-to-use-on-windows-forms.md). Если элемент управления <xref:System.Windows.Forms.Control.OnPaint%2A> не указан в качестве элемента, вы не можете изменить его внешний вид, переопределив этот метод. Дополнительные сведения о пользовательском оформлении см. в разделе [Рисование и отрисовка пользовательского элемента управления](custom-control-painting-and-rendering.md).

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

## <a name="see-also"></a>См. также раздел

- [Создание собственных элементов управления](varieties-of-custom-controls.md)
- [Практическое руководство. Наследование класса Control](how-to-inherit-from-the-control-class.md)
- [Практическое руководство. Наследование класса UserControl.](how-to-inherit-from-the-usercontrol-class.md)
- [Практическое руководство. Создание элементов управления для форм Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Пошаговая прогулка: Наследование от управления формами Windows](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
