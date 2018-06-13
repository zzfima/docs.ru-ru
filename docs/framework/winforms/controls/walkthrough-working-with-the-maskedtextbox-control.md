---
title: Пример. Работа с элементом управления MaskedTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: bcca6c5f5481d351a39a4e71532cc0f006075128
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538445"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>Пример. Работа с элементом управления MaskedTextBox
В данном пошаговом руководстве представлены следующие задачи.  
  
-   Инициализация <xref:System.Windows.Forms.MaskedTextBox> управления  
  
-   С помощью <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> обработчик событий для оповещения пользователя, когда символ не соответствует маске  
  
-   Присвоение типа <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> свойство и с помощью <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> обработчик событий, чтобы предупреждать пользователей при попытках зафиксировать значение недопустимо для типа  
  
## <a name="creating-the-project-and-adding-a-control"></a>Создание проекта и добавление элемента управления  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>Чтобы добавить элемент управления MaskedTextBox в форму  
  
1.  Откройте форму, на котором требуется разместить <xref:System.Windows.Forms.MaskedTextBox> элемента управления.  
  
2.  Перетащите <xref:System.Windows.Forms.MaskedTextBox> управления из **элементов** в форму.  
  
3.  Щелкните правой кнопкой мыши элемент управления и выберите **свойства**. В **свойства** выберите **маска** свойство и нажмите кнопку **...**  (многоточие) рядом с именем свойства.  
  
4.  В **маска ввода** выберите **короткого формата даты** маску и нажмите кнопку **ОК**.  
  
5.  В **свойства** задайте <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> свойства `true`. Это свойство создает короткий звуковой сигнал всякий раз когда пользователь пытается ввести знак, нарушающий определение маски.  
  
 Сводка символов, которые поддерживает свойство маски, в разделе «Примечания» <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> свойство.  
  
## <a name="alert-the-user-to-input-errors"></a>Оповещать пользователя об ошибках ввода  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>Добавьте всплывающую подсказку об отклоненном вводе  
  
1.  Вернитесь к **элементов** и добавьте <xref:System.Windows.Forms.ToolTip> в форму.  
  
2.  Создайте обработчик событий для <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> событие, вызываемое <xref:System.Windows.Forms.ToolTip> при возникновении ошибок на входе. Всплывающая подсказка остается видимым пять секунд, или пока пользователь его щелкает.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>Предупредить пользователя о тип, который является недопустимым  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>Добавьте всплывающую подсказку о недопустимых типах данных  
  
1.  На форме <xref:System.Windows.Forms.Form.Load> обработчика событий, назначьте <xref:System.Type> , представляющий <xref:System.DateTime> тип <xref:System.Windows.Forms.MaskedTextBox> элемента управления <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> свойство:  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2.  Добавьте обработчик событий для события <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>.  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [Элемент управления MaskedTextBox](../../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)
