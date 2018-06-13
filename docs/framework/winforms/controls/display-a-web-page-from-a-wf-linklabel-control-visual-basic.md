---
title: Практическое руководство. Отображение веб-страницы из элемента управления LinkLabel в Windows Forms (Visual Basic)
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
ms.openlocfilehash: a9964c8d333ea87dd995ec9111acc1a8ac1e79b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524187"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a><span data-ttu-id="8bb02-102">Практическое руководство. Отображение веб-страницы из элемента управления LinkLabel в Windows Forms (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8bb02-102">How to: Display a Web Page from a Windows Forms LinkLabel Control (Visual Basic)</span></span>
<span data-ttu-id="8bb02-103">Этот пример выводит на веб-страницу в браузере по умолчанию, когда пользователь щелкает Windows Forms <xref:System.Windows.Forms.LinkLabel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8bb02-103">This example displays a Web page in the default browser when a user clicks a Windows Forms <xref:System.Windows.Forms.LinkLabel> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bb02-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8bb02-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="8bb02-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="8bb02-105">Compiling the Code</span></span>  
 <span data-ttu-id="8bb02-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="8bb02-106">This example requires:</span></span>  
  
-   <span data-ttu-id="8bb02-107">Формы Windows Forms с именем `Form1`.</span><span class="sxs-lookup"><span data-stu-id="8bb02-107">A Windows Form named `Form1`.</span></span>  
  
-   <span data-ttu-id="8bb02-108">элемент управления <xref:System.Windows.Forms.LinkLabel> с именем `LinkLabel1`;</span><span class="sxs-lookup"><span data-stu-id="8bb02-108">A <xref:System.Windows.Forms.LinkLabel> control named `LinkLabel1`.</span></span>  
  
-   <span data-ttu-id="8bb02-109">Активное подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="8bb02-109">An active Internet connection.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8bb02-110">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8bb02-110">.NET Framework Security</span></span>  
 <span data-ttu-id="8bb02-111">Вызов <xref:System.Diagnostics.Process.Start%2A> метод требует полного доверия.</span><span class="sxs-lookup"><span data-stu-id="8bb02-111">The call to the <xref:System.Diagnostics.Process.Start%2A> method requires full trust.</span></span> <span data-ttu-id="8bb02-112">Дополнительные сведения см. в разделе <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="8bb02-112">For more information, see <xref:System.Security.SecurityException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bb02-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8bb02-113">See Also</span></span>  
 <xref:System.Windows.Forms.LinkLabel>  
 [<span data-ttu-id="8bb02-114">Элемент управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="8bb02-114">LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
