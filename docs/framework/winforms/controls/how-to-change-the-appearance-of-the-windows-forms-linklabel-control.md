---
title: Изменение внешнего вида управления LinkLabel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: df66991289373a05fc7c27b7768a96643e3bbae0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142134"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="307f0-102">Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="307f0-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="307f0-103">Вы можете изменить текст, <xref:System.Windows.Forms.LinkLabel> отображаемый элементом управления, в соответствии с различными целями.</span><span class="sxs-lookup"><span data-stu-id="307f0-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="307f0-104">Например, обычно пользователь указывает, что текст можно нажать, установив текст для отображания определенного цвета с подчеркиванием.</span><span class="sxs-lookup"><span data-stu-id="307f0-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="307f0-105">После того, как пользователь нажимает на текст, цвет меняется на другой цвет.</span><span class="sxs-lookup"><span data-stu-id="307f0-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="307f0-106">Чтобы контролировать это поведение, вы можете установить <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>пять <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> различных свойств: <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, и свойства.</span><span class="sxs-lookup"><span data-stu-id="307f0-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="307f0-107">Изменить внешний вид элемента управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="307f0-107">To change the appearance of a LinkLabel control</span></span>  
  
1. <span data-ttu-id="307f0-108">Установите <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> и свойства цвета, которые вы хотите.</span><span class="sxs-lookup"><span data-stu-id="307f0-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="307f0-109">Это можно сделать как в программном плане, так и во время проектирования в окне **Свойств.**</span><span class="sxs-lookup"><span data-stu-id="307f0-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2. <span data-ttu-id="307f0-110">Установите <xref:System.Windows.Forms.LinkLabel.Text%2A> свойство на соответствующую подпись.</span><span class="sxs-lookup"><span data-stu-id="307f0-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="307f0-111">Это можно сделать как в программном плане, так и во время проектирования в окне **Свойств.**</span><span class="sxs-lookup"><span data-stu-id="307f0-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. <span data-ttu-id="307f0-112">Установите <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> свойство, чтобы определить, какая часть подписи будет указана в виде ссылки.</span><span class="sxs-lookup"><span data-stu-id="307f0-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="307f0-113">Значение <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> представлено двумя <xref:System.Windows.Forms.LinkArea> числами, положением исходного символа и числом символов.</span><span class="sxs-lookup"><span data-stu-id="307f0-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="307f0-114">Это можно сделать как в программном плане, так и во время проектирования в окне **Свойств.**</span><span class="sxs-lookup"><span data-stu-id="307f0-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. <span data-ttu-id="307f0-115">Установите <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>свойство, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline> <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>или .</span><span class="sxs-lookup"><span data-stu-id="307f0-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="307f0-116">Если он установлен <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>на, часть подписи <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> определяется будет только подчеркнута, когда указатель опирается на него.</span><span class="sxs-lookup"><span data-stu-id="307f0-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5. <span data-ttu-id="307f0-117">В <xref:System.Windows.Forms.LinkLabel.LinkClicked> обработчике <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> событий `true`установите свойство на .</span><span class="sxs-lookup"><span data-stu-id="307f0-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="307f0-118">Когда ссылка была посещена, это обычная практика, чтобы изменить его внешний вид в некотором роде, как правило, по цвету.</span><span class="sxs-lookup"><span data-stu-id="307f0-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="307f0-119">Текст будет меняться на цвет, указанный свойством. <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A></span><span class="sxs-lookup"><span data-stu-id="307f0-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="307f0-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="307f0-120">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="307f0-121">Общие сведения об элементе управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="307f0-121">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="307f0-122">Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="307f0-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="307f0-123">Элемент управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="307f0-123">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
