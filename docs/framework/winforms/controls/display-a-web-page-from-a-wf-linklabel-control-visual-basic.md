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
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>Практическое руководство. Отображение веб-страницы из элемента управления LinkLabel в Windows Forms (Visual Basic)
В этом примере отображается веб-страница в браузере по умолчанию, когда пользователь щелкает элемент управления Windows Forms <xref:System.Windows.Forms.LinkLabel>.  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- Форма Windows Forms с именем `Form1`.  
  
- элемент управления <xref:System.Windows.Forms.LinkLabel> с именем `LinkLabel1`;  
  
- Активное подключение к Интернету.  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework  
 Вызов метода <xref:System.Diagnostics.Process.Start%2A> требует полного доверия. Дополнительные сведения см. в разделе <xref:System.Security.SecurityException>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.LinkLabel>
- [Элемент управления LinkLabel](linklabel-control-windows-forms.md)
