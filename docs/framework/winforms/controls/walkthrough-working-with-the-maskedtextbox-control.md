---
title: "Пример. Работа с элементом управления MaskedTextBox | Microsoft Docs"
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
  - "ввод, управление для обеспечения действительности"
  - "MaskedTextBox - элемент управления [Windows Forms], проверка"
  - "MaskedTextBox - элемент управления [Windows Forms], пошаговые руководства"
  - "текст, элементы управления для ввода"
  - "ввод данных пользователем, управление"
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Пример. Работа с элементом управления MaskedTextBox
В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   Инициализация элемента управления <xref:System.Windows.Forms.MaskedTextBox>.  
  
-   Использование обработчика событий <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> для оповещения пользователя, когда знак не соответствует маске  
  
-   Присвоение типа свойству <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> и использование обработчика событий <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> для оповещения пользователя в случаях, когда передаваемое значение имеет недопустимый тип  
  
## Создание проекта и добавление элемента управления  
  
#### Для добавления элемента управления MaskedTextBox в форму  
  
1.  Откройте форму, в которую нужно поместить элемент управления <xref:System.Windows.Forms.MaskedTextBox>.  
  
2.  Перетащите элемент управления <xref:System.Windows.Forms.MaskedTextBox> из **панели элементов** в форму.  
  
3.  Щелкните элемент управления правой кнопкой мыши и выберите **Свойства**.  В окне **Свойства** выберите свойство **Маска** и нажмите кнопку **...** \(многоточие\) рядом с именем свойства.  
  
4.  В окне **Маска ввода** выберите **Краткий формат даты** и нажмите кнопку **ОК**.  
  
5.  В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> значение `true`.  Это свойство создает короткий звуковой сигнал всякий раз, когда пользователь пытается ввести знак, нарушающий определение маски.  
  
 Сводка символов, поддерживаемых свойством маски, приведена в разделе "Примечания" для свойства <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>.  
  
## Оповещение пользователя об ошибках ввода  
  
#### Добавьте всплывающую подсказку об отклоненном вводе  
  
1.  Вернитесь в **область элементов** и добавьте <xref:System.Windows.Forms.ToolTip> в форму.  
  
2.  Создайте обработчик событий <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected>, создающий <xref:System.Windows.Forms.ToolTip> в случае ошибок ввода.  Всплывающая подсказка отображается в течение пяти секунд или до тех пор, пока ее не щелкнет пользователь.  
  
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
  
## Оповестите пользователя о том, что введен знак недопустимого типа  
  
#### Добавьте всплывающую подсказку о недопустимых типах данных  
  
1.  В обработчике событий <xref:System.Windows.Forms.Form.Load> формы назначьте объект <xref:System.Type>, представляющий тип <xref:System.DateTime> свойству <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> элемента управления <xref:System.Windows.Forms.MaskedTextBox>:  
  
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
  
2.  Добавьте обработчик событий <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>.  
  
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
  
## См. также  
 <xref:System.Windows.Forms.MaskedTextBox>   
 [Пример элемента управления MaskedTextBox](../../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)