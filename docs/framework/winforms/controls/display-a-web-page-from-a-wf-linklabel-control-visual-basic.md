---
title: "Практическое руководство. Отображение веб-страницы из элемента управления LinkLabel в Windows Forms (Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
f1_keywords: LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba5ba3b29bab148087e0f8b80b3f1c43aa74e761
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a><span data-ttu-id="2ae25-102">Практическое руководство. Отображение веб-страницы из элемента управления LinkLabel в Windows Forms (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ae25-102">How to: Display a Web Page from a Windows Forms LinkLabel Control (Visual Basic)</span></span>
<span data-ttu-id="2ae25-103">Этот пример выводит на веб-страницу в браузере по умолчанию, когда пользователь щелкает Windows Forms <xref:System.Windows.Forms.LinkLabel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2ae25-103">This example displays a Web page in the default browser when a user clicks a Windows Forms <xref:System.Windows.Forms.LinkLabel> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ae25-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2ae25-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ae25-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2ae25-105">Compiling the Code</span></span>  
 <span data-ttu-id="2ae25-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="2ae25-106">This example requires:</span></span>  
  
-   <span data-ttu-id="2ae25-107">Формы Windows Forms с именем `Form1`.</span><span class="sxs-lookup"><span data-stu-id="2ae25-107">A Windows Form named `Form1`.</span></span>  
  
-   <span data-ttu-id="2ae25-108">элемент управления <xref:System.Windows.Forms.LinkLabel> с именем `LinkLabel1`;</span><span class="sxs-lookup"><span data-stu-id="2ae25-108">A <xref:System.Windows.Forms.LinkLabel> control named `LinkLabel1`.</span></span>  
  
-   <span data-ttu-id="2ae25-109">Активное подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="2ae25-109">An active Internet connection.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2ae25-110">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2ae25-110">.NET Framework Security</span></span>  
 <span data-ttu-id="2ae25-111">Вызов <xref:System.Diagnostics.Process.Start%2A> метод требует полного доверия.</span><span class="sxs-lookup"><span data-stu-id="2ae25-111">The call to the <xref:System.Diagnostics.Process.Start%2A> method requires full trust.</span></span> <span data-ttu-id="2ae25-112">Дополнительные сведения см. в разделе <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="2ae25-112">For more information, see <xref:System.Security.SecurityException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae25-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2ae25-113">See Also</span></span>  
 <xref:System.Windows.Forms.LinkLabel>  
 [<span data-ttu-id="2ae25-114">Элемент управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="2ae25-114">LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
