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
ms.openlocfilehash: db32b3ec88a07747ea3e286af9f04edce3f1ba3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182057"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>Пример. Работа с элементом управления MaskedTextBox
В данном пошаговом руководстве представлены следующие задачи.  
  
- Инициализация <xref:System.Windows.Forms.MaskedTextBox> управления  
  
- Использование <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> обработчика событий для оповещения пользователя о том, что персонаж не соответствует маске  
  
- Назначение типа <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> к свойству и <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> использование обработчика событий для оповещения пользователя о том, что значение, которое он пытается совершить, не является действительным для типа  
  
## <a name="creating-the-project-and-adding-a-control"></a>Создание проекта и добавление элемента управления  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>Добавление элемента управления MaskedTextBox в форму  
  
1. Откройте форму, на которой <xref:System.Windows.Forms.MaskedTextBox> вы хотите разместить элемент управления.  
  
2. Перетащите <xref:System.Windows.Forms.MaskedTextBox> элемент управления из **ящика инструментов** в форму.  
  
3. Нажмите правой кнопкой мыши управления и выбрать **Свойства**. В окне **Свойства** выберите свойство **Маска** и нажмите кнопку **...** (ellipsis) рядом с именем свойства.  
  
4. В диалоговом окне **ввода маски** выберите маску **«Короткая дата»** и **нажмите OK.**  
  
5. В **Properties** окне Свойства <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> установить свойство `true`. Это свойство вызывает короткий звуковой сигнал, чтобы звучать каждый раз, когда пользователь пытается ввести символ, который нарушает определение маски.  
  
 Для краткого изложения символов, которые поддерживает свойство <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Маска, см.  
  
## <a name="alert-the-user-to-input-errors"></a>Предупредите пользователя об ошибках ввода  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>Добавить наконечник шара для отклоненного ввода маски  
  
1. Вернитесь в **Toolbox** <xref:System.Windows.Forms.ToolTip> и добавьте в свою форму.  
  
2. Создайте обработчик <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> событий, <xref:System.Windows.Forms.ToolTip> который повышает, когда происходит ошибка ввода. Наконечник шарика остается видимым в течение пяти секунд, или до тех пор, пока пользователь не нажмет на него.  
  
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
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>Оповещение пользователя о недопустимом типе  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>Добавление наконечника шара для недействительных типов данных  
  
1. В обработчике <xref:System.Windows.Forms.Form.Load> событий вашей <xref:System.Type> формы присвоите объекту, представляющему <xref:System.DateTime> тип, свойство <xref:System.Windows.Forms.MaskedTextBox> <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> управления:  
  
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
  
2. Добавьте обработчик событий для события <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.MaskedTextBox>
- [Элемент управления MaskedTextBox](maskedtextbox-control-windows-forms.md)
