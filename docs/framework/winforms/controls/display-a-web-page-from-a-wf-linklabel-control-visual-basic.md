---
title: Отображение веб-страницы из элемента управления LinkLabel (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
ms.openlocfilehash: 75373d55b7bc5ef11e39d5b9546996cb1c4f6f7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745925"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a><span data-ttu-id="c12b4-102">Практическое руководство. Отображение веб-страницы из элемента управления LinkLabel в Windows Forms (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c12b4-102">How to: Display a Web Page from a Windows Forms LinkLabel Control (Visual Basic)</span></span>
<span data-ttu-id="c12b4-103">В этом примере отображается веб-страница в браузере по умолчанию, когда пользователь щелкает элемент управления Windows Forms <xref:System.Windows.Forms.LinkLabel>.</span><span class="sxs-lookup"><span data-stu-id="c12b4-103">This example displays a Web page in the default browser when a user clicks a Windows Forms <xref:System.Windows.Forms.LinkLabel> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c12b4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c12b4-104">Example</span></span>  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c12b4-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c12b4-105">Compiling the Code</span></span>  
 <span data-ttu-id="c12b4-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="c12b4-106">This example requires:</span></span>  
  
- <span data-ttu-id="c12b4-107">Форма Windows Forms с именем `Form1`.</span><span class="sxs-lookup"><span data-stu-id="c12b4-107">A Windows Form named `Form1`.</span></span>  
  
- <span data-ttu-id="c12b4-108">элемент управления <xref:System.Windows.Forms.LinkLabel> с именем `LinkLabel1`;</span><span class="sxs-lookup"><span data-stu-id="c12b4-108">A <xref:System.Windows.Forms.LinkLabel> control named `LinkLabel1`.</span></span>  
  
- <span data-ttu-id="c12b4-109">Активное подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="c12b4-109">An active Internet connection.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c12b4-110">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c12b4-110">.NET Framework Security</span></span>  
 <span data-ttu-id="c12b4-111">Вызов метода <xref:System.Diagnostics.Process.Start%2A> требует полного доверия.</span><span class="sxs-lookup"><span data-stu-id="c12b4-111">The call to the <xref:System.Diagnostics.Process.Start%2A> method requires full trust.</span></span> <span data-ttu-id="c12b4-112">Для получения дополнительной информации см. <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="c12b4-112">For more information, see <xref:System.Security.SecurityException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c12b4-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="c12b4-113">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel>
- [<span data-ttu-id="c12b4-114">Элемент управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="c12b4-114">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
