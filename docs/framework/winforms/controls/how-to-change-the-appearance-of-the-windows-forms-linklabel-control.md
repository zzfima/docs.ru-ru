---
title: Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms
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
ms.openlocfilehash: be2f6e8e10d9f9b23b4f57fa696f1fb88c4726c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105031"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="d8c41-102">Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d8c41-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="d8c41-103">Можно изменить текст, отображаемый элементом <xref:System.Windows.Forms.LinkLabel> управления для различных целей.</span><span class="sxs-lookup"><span data-stu-id="d8c41-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="d8c41-104">Например это распространенная практика, чтобы уведомить пользователя, что текст можно щелкнуть мышью текст, появляющийся определенным цветом и подчеркиванием.</span><span class="sxs-lookup"><span data-stu-id="d8c41-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="d8c41-105">Пользователь щелкает этот текст, цвет меняется на другой цвет.</span><span class="sxs-lookup"><span data-stu-id="d8c41-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="d8c41-106">Чтобы контролировать это поведение, можно задать пять различных свойств: <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, и <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="d8c41-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="d8c41-107">Чтобы изменить внешний вид элемента управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="d8c41-107">To change the appearance of a LinkLabel control</span></span>  
  
1.  <span data-ttu-id="d8c41-108">Задайте <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> и <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> свойства, чтобы нужные цвета.</span><span class="sxs-lookup"><span data-stu-id="d8c41-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="d8c41-109">Это можно сделать программным образом или во время разработки в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="d8c41-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
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
  
2.  <span data-ttu-id="d8c41-110">Задайте <xref:System.Windows.Forms.LinkLabel.Text%2A> свойство соответствующий заголовок.</span><span class="sxs-lookup"><span data-stu-id="d8c41-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="d8c41-111">Это можно сделать программным образом или во время разработки в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="d8c41-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  <span data-ttu-id="d8c41-112">Задать <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> свойства, чтобы определить, какая часть заголовка будет представлена в качестве ссылки.</span><span class="sxs-lookup"><span data-stu-id="d8c41-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="d8c41-113"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Представлено <xref:System.Windows.Forms.LinkArea> содержащий два числа, положение начального знака и число символов.</span><span class="sxs-lookup"><span data-stu-id="d8c41-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="d8c41-114">Это можно сделать программным образом или во время разработки в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="d8c41-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  <span data-ttu-id="d8c41-115">Задайте <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> свойства <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, или <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span><span class="sxs-lookup"><span data-stu-id="d8c41-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="d8c41-116">Если он становится равным <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, часть заголовка, определяется <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> будет подчеркнуто только при наведении указателя на нем.</span><span class="sxs-lookup"><span data-stu-id="d8c41-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5.  <span data-ttu-id="d8c41-117">В <xref:System.Windows.Forms.LinkLabel.LinkClicked> задать обработчик событий, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="d8c41-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="d8c41-118">При ссылке это распространенная практика, чтобы изменить его внешний вид, обычно по цвету.</span><span class="sxs-lookup"><span data-stu-id="d8c41-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="d8c41-119">Текст изменится на цвет, определенный параметром <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="d8c41-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d8c41-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d8c41-120">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="d8c41-121">Общие сведения об элементе управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="d8c41-121">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="d8c41-122">Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d8c41-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="d8c41-123">Элемент управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="d8c41-123">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
