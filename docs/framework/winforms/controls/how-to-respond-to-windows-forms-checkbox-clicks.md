---
title: Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms
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
ms.openlocfilehash: 7ff6b2aad9ef0775547af57f11af28839e69637c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914984"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="55919-102">Практическое руководство. Обработка события щелчка элемента управления CheckBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55919-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="55919-103">Когда пользователь щелкает элемент управления Windows Forms <xref:System.Windows.Forms.CheckBox> <xref:System.Windows.Forms.Control.Click> , возникает событие.</span><span class="sxs-lookup"><span data-stu-id="55919-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="55919-104">Приложение можно запрограммировать для выполнения некоторых действий в зависимости от состояния флажка.</span><span class="sxs-lookup"><span data-stu-id="55919-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="55919-105">Реагирование на нажатия кнопки CheckBox</span><span class="sxs-lookup"><span data-stu-id="55919-105">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="55919-106">В обработчике <xref:System.Windows.Forms.CheckBox.Checked%2A>событийиспользуйте свойство для определения состояния элемента управления и выполнения необходимых действий. <xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="55919-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    > <span data-ttu-id="55919-107">Если пользователь пытается дважды щелкнуть <xref:System.Windows.Forms.CheckBox> элемент управления, каждый щелчок будет обрабатываться отдельно, то есть <xref:System.Windows.Forms.CheckBox> элемент управления не поддерживает событие двойного щелчка.</span><span class="sxs-lookup"><span data-stu-id="55919-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="55919-108">Если свойство имеет `true` значение (по умолчанию), <xref:System.Windows.Forms.CheckBox> то при щелчке автоматически выбирается или удаляется. <xref:System.Windows.Forms.CheckBox.AutoCheck%2A></span><span class="sxs-lookup"><span data-stu-id="55919-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="55919-109">В противном случае необходимо вручную задать <xref:System.Windows.Forms.CheckBox.Checked%2A> свойство <xref:System.Windows.Forms.Control.Click> при возникновении события.</span><span class="sxs-lookup"><span data-stu-id="55919-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="55919-110">Можно также использовать <xref:System.Windows.Forms.CheckBox> элемент управления для определения курса действий.</span><span class="sxs-lookup"><span data-stu-id="55919-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="55919-111">Определение курса действий при нажатии на флажок</span><span class="sxs-lookup"><span data-stu-id="55919-111">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="55919-112">Используйте оператор Case для запроса значения <xref:System.Windows.Forms.CheckBox.CheckState%2A> свойства, чтобы определить направление действия.</span><span class="sxs-lookup"><span data-stu-id="55919-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="55919-113">Если свойство имеет `true`значение, <xref:System.Windows.Forms.CheckBox.CheckState%2A> свойство может возвращать три возможных значения, которые представляют проверяемую рамку, флажок снят или третье неопределенное состояние, при котором поле отображается серым цветом. <xref:System.Windows.Forms.CheckBox.ThreeState%2A> внешний вид, указывающий, что параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="55919-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    > <span data-ttu-id="55919-114">`true` <xref:System.Windows.Forms.CheckBox.Checked%2A> `true` Если свойство имеет значение, свойство возвращается для<xref:System.Windows.Forms.CheckState.Checked> и .<xref:System.Windows.Forms.CheckState.Indeterminate> <xref:System.Windows.Forms.CheckBox.ThreeState%2A></span><span class="sxs-lookup"><span data-stu-id="55919-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55919-115">См. также</span><span class="sxs-lookup"><span data-stu-id="55919-115">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="55919-116">Общие сведения об элементе управления CheckBox</span><span class="sxs-lookup"><span data-stu-id="55919-116">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="55919-117">Практическое руководство. Настройка параметров с помощью элементов управления CheckBox Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55919-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="55919-118">Элемент управления CheckBox</span><span class="sxs-lookup"><span data-stu-id="55919-118">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
