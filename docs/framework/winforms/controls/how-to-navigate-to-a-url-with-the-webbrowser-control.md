---
title: "Практическое руководство. Переход по заданному URL с помощью элемента управления WebBrowser | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WebBrowser.Navigate"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "примеры [Windows Forms], WebBrowser - элемент управления"
  - "URL-адреса, переход к"
  - "WebBrowser - элемент управления [Windows Forms], примеры"
  - "WebBrowser - элемент управления [Windows Forms], переход к URL-адресу"
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Переход по заданному URL с помощью элемента управления WebBrowser
В следующем примере кода демонстрируется переход элемента управления <xref:System.Windows.Forms.WebBrowser> к определенному URL\-адресу.  
  
 Чтобы определить момент, когда новый документ полностью загружен, необходимо обработать событие <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>.  Описание этого события см. в разделе [Практическое руководство. Печать с использованием элемента управления WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md).  
  
## Пример  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.WebBrowser> с именем `webBrowser1`.  
  
-   Ссылки на сборки `System` и `System.Windows.Forms`.  
  
## См. также  
 <xref:System.Windows.Forms.WebBrowser>   
 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=fullName>   
 <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=fullName>   
 <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=fullName>   
 [Элемент управления WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)   
 [Практическое руководство. Печать с использованием элемента управления WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)