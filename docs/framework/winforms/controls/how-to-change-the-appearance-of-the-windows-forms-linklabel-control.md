---
title: Изменение внешнего вида элемента управления LinkLabel
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
ms.openlocfilehash: 0b38722fb1647ea215c3bb8978dd3f54b300a0e0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746630"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="388e8-102">Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="388e8-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="388e8-103">Текст, отображаемый элементом управления <xref:System.Windows.Forms.LinkLabel>, можно изменить в соответствии с различными целями.</span><span class="sxs-lookup"><span data-stu-id="388e8-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="388e8-104">Например, обычно можно указать пользователю на то, что текст может быть щелчком, чтобы текст отображался в определенном цвете с подчеркиванием.</span><span class="sxs-lookup"><span data-stu-id="388e8-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="388e8-105">После того, как пользователь щелкнет текст, цвет изменится на другой цвет.</span><span class="sxs-lookup"><span data-stu-id="388e8-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="388e8-106">Для управления этим поведением можно задать пять различных свойств: <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>и <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>.</span><span class="sxs-lookup"><span data-stu-id="388e8-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="388e8-107">Изменение внешнего вида элемента управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="388e8-107">To change the appearance of a LinkLabel control</span></span>  
  
1. <span data-ttu-id="388e8-108">Задайте для свойств <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> и <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> нужные цвета.</span><span class="sxs-lookup"><span data-stu-id="388e8-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="388e8-109">Это можно сделать либо программно, либо во время разработки в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="388e8-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
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
  
2. <span data-ttu-id="388e8-110">Задайте для свойства <xref:System.Windows.Forms.LinkLabel.Text%2A> соответствующий заголовок.</span><span class="sxs-lookup"><span data-stu-id="388e8-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="388e8-111">Это можно сделать либо программно, либо во время разработки в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="388e8-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. <span data-ttu-id="388e8-112">Задайте свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, чтобы определить, какая часть заголовка будет указана как ссылка.</span><span class="sxs-lookup"><span data-stu-id="388e8-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="388e8-113"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A> значение представляется с <xref:System.Windows.Forms.LinkArea>, содержащим два числа: начальную точку символа и число символов.</span><span class="sxs-lookup"><span data-stu-id="388e8-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="388e8-114">Это можно сделать либо программно, либо во время разработки в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="388e8-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. <span data-ttu-id="388e8-115">Задайте для свойства <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> значение <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>или <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span><span class="sxs-lookup"><span data-stu-id="388e8-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="388e8-116">Если задано значение <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, часть заголовка, определяемая <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, будет подчеркнута только при наведении на нее указателя.</span><span class="sxs-lookup"><span data-stu-id="388e8-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5. <span data-ttu-id="388e8-117">В обработчике событий <xref:System.Windows.Forms.LinkLabel.LinkClicked> задайте для свойства <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="388e8-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="388e8-118">При посещении ссылки часто бывает проще изменить внешний вид, обычно по цвету.</span><span class="sxs-lookup"><span data-stu-id="388e8-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="388e8-119">Текст изменится на цвет, указанный в свойстве <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="388e8-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="388e8-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="388e8-120">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="388e8-121">Общие сведения об элементе управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="388e8-121">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="388e8-122">Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="388e8-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="388e8-123">Элемент управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="388e8-123">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
