---
title: Как выполнить Обработка события в Windows Forms щелчка элемента управления CheckBox
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
ms.openlocfilehash: cf9a7c51c0054c34dbce40f3a2dfa68c62f3a4e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726329"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="2aaf7-102">Как выполнить Обработка события в Windows Forms щелчка элемента управления CheckBox</span><span class="sxs-lookup"><span data-stu-id="2aaf7-102">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="2aaf7-103">Каждый раз, когда пользователь щелкает форм Windows <xref:System.Windows.Forms.CheckBox> управления <xref:System.Windows.Forms.Control.Click> событием.</span><span class="sxs-lookup"><span data-stu-id="2aaf7-103">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="2aaf7-104">Можно программировать приложения для выполнения некоторых операций, в зависимости от состояния флажка.</span><span class="sxs-lookup"><span data-stu-id="2aaf7-104">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="2aaf7-105">Реагировать на щелчка элемента управления CheckBox</span><span class="sxs-lookup"><span data-stu-id="2aaf7-105">To respond to CheckBox clicks</span></span>  
  
1.  <span data-ttu-id="2aaf7-106">В <xref:System.Windows.Forms.Control.Click> обработчик событий, используйте <xref:System.Windows.Forms.CheckBox.Checked%2A> свойство, чтобы определить состояние элемента управления, а также выполнять любые необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="2aaf7-106">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
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
    >  <span data-ttu-id="2aaf7-107">Если пользователь пытается получить дважды щелкните <xref:System.Windows.Forms.CheckBox> элемента управления, каждый щелчок будет обрабатываться отдельно, то есть, <xref:System.Windows.Forms.CheckBox> управления не поддерживает события двойного щелчка.</span><span class="sxs-lookup"><span data-stu-id="2aaf7-107">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2aaf7-108">Когда <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> свойство `true` (по умолчанию), <xref:System.Windows.Forms.CheckBox> автоматически установлен или снят, при щелчке.</span><span class="sxs-lookup"><span data-stu-id="2aaf7-108">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="2aaf7-109">В противном случае необходимо вручную задать <xref:System.Windows.Forms.CheckBox.Checked%2A> свойство при <xref:System.Windows.Forms.Control.Click> событием.</span><span class="sxs-lookup"><span data-stu-id="2aaf7-109">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="2aaf7-110">Можно также использовать <xref:System.Windows.Forms.CheckBox> управления, чтобы определить направление дальнейших действий.</span><span class="sxs-lookup"><span data-stu-id="2aaf7-110">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="2aaf7-111">Чтобы определить порядок действий при типа "флажок" нажата</span><span class="sxs-lookup"><span data-stu-id="2aaf7-111">To determine a course of action when a check box is clicked</span></span>  
  
1.  <span data-ttu-id="2aaf7-112">Оператор case для запроса значения <xref:System.Windows.Forms.CheckBox.CheckState%2A> свойства, чтобы определить направление дальнейших действий.</span><span class="sxs-lookup"><span data-stu-id="2aaf7-112">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="2aaf7-113">Когда <xref:System.Windows.Forms.CheckBox.ThreeState%2A> свойству `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> свойство может вернуть три возможных значения, представляющие флажком, поле снятому или сторонним неопределенном состоянии, в котором отображается поле с серым цветом внешний вид, чтобы указать параметр будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="2aaf7-113">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
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
    >  <span data-ttu-id="2aaf7-114">Когда <xref:System.Windows.Forms.CheckBox.ThreeState%2A> свойству `true`, <xref:System.Windows.Forms.CheckBox.Checked%2A> возвращает `true` для обоих <xref:System.Windows.Forms.CheckState.Checked> и <xref:System.Windows.Forms.CheckState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="2aaf7-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aaf7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2aaf7-115">See also</span></span>
- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="2aaf7-116">Общие сведения об элементе управления CheckBox</span><span class="sxs-lookup"><span data-stu-id="2aaf7-116">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="2aaf7-117">Практическое руководство. Настройка параметров с помощью элементов управления Windows Forms CheckBox</span><span class="sxs-lookup"><span data-stu-id="2aaf7-117">How to: Set Options with Windows Forms CheckBox Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="2aaf7-118">Элемент управления CheckBox</span><span class="sxs-lookup"><span data-stu-id="2aaf7-118">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
