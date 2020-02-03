---
title: Реагирование на нажатия флажков
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
ms.openlocfilehash: ba2afb52939a6274978ce725dac19b5622419b99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735661"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="2a16f-102">Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a16f-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="2a16f-103">Когда пользователь щелкает элемент управления Windows Forms <xref:System.Windows.Forms.CheckBox>, возникает событие <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="2a16f-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="2a16f-104">Приложение можно запрограммировать для выполнения некоторых действий в зависимости от состояния флажка.</span><span class="sxs-lookup"><span data-stu-id="2a16f-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="2a16f-105">Реагирование на нажатия кнопки CheckBox</span><span class="sxs-lookup"><span data-stu-id="2a16f-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="2a16f-106">В обработчике событий <xref:System.Windows.Forms.Control.Click> используйте свойство <xref:System.Windows.Forms.CheckBox.Checked%2A>, чтобы определить состояние элемента управления и выполнить все необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="2a16f-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the   
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the   
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="2a16f-107">Если пользователь пытается дважды щелкнуть элемент управления <xref:System.Windows.Forms.CheckBox>, каждый щелчок будет обрабатываться отдельно. то есть элемент управления <xref:System.Windows.Forms.CheckBox> не поддерживает событие двойного щелчка.</span><span class="sxs-lookup"><span data-stu-id="2a16f-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2a16f-108">Если свойство <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> `true` (по умолчанию), <xref:System.Windows.Forms.CheckBox> автоматически выбирается или удаляется при щелчке.</span><span class="sxs-lookup"><span data-stu-id="2a16f-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="2a16f-109">В противном случае необходимо вручную задать свойство <xref:System.Windows.Forms.CheckBox.Checked%2A> при возникновении события <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="2a16f-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="2a16f-110">Для определения курса действий можно также использовать элемент управления <xref:System.Windows.Forms.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="2a16f-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="2a16f-111">Определение курса действий при нажатии на флажок</span><span class="sxs-lookup"><span data-stu-id="2a16f-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="2a16f-112">Используйте оператор Case для запроса значения свойства <xref:System.Windows.Forms.CheckBox.CheckState%2A>, чтобы определить направление действия.</span><span class="sxs-lookup"><span data-stu-id="2a16f-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="2a16f-113">Если свойство <xref:System.Windows.Forms.CheckBox.ThreeState%2A> имеет значение `true`, то свойство <xref:System.Windows.Forms.CheckBox.CheckState%2A> может возвращать три возможных значения, которые представляют собой проверяемую рамку, флажок снят или третье неопределенное состояние, при котором окно отображается серым цветом, чтобы указать, что параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="2a16f-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select   
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="2a16f-114">Если свойство <xref:System.Windows.Forms.CheckBox.ThreeState%2A> имеет значение `true`, свойство <xref:System.Windows.Forms.CheckBox.Checked%2A> возвращает `true` для <xref:System.Windows.Forms.CheckState.Checked> и <xref:System.Windows.Forms.CheckState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="2a16f-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a16f-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2a16f-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="2a16f-116">Общие сведения об элементе управления CheckBox</span><span class="sxs-lookup"><span data-stu-id="2a16f-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="2a16f-117">Практическое руководство. Задание параметров с помощью элементов управления CheckBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a16f-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="2a16f-118">Элемент управления CheckBox</span><span class="sxs-lookup"><span data-stu-id="2a16f-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
