---
title: "Безопасность элемента управления WebBrowser | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "безопасность [Windows Forms], WebBrowser - элемент управления"
  - "WebBrowser - элемент управления [Windows Forms], безопасность"
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Безопасность элемента управления WebBrowser
Элемент управления <xref:System.Windows.Forms.WebBrowser> предназначен для работы только в среде с полным доверием.  Отображаемое в элементе управления HTML\-содержимое может поступать от внешних веб\-серверов и может содержать неуправляемый код в форме скриптов или веб\-элементов управления.  Если в такой ситуации используется элемент управления <xref:System.Windows.Forms.WebBrowser>, этот элемент управления является не менее безопасным, чем Internet Explorer, причем управляемый элемент управления <xref:System.Windows.Forms.WebBrowser> не предотвращает запуск такого неуправляемого кода.  
  
 Дополнительные сведения о безопасности, связанные с базовым элементом управления ActiveX `WebBrowser`, см. в разделе [WebBrowser Control](http://go.microsoft.com/fwlink/?LinkId=198812).  
  
## См. также  
 <xref:System.Windows.Forms.WebBrowser>   
 [Общие сведения об элементе управления WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)   
 [WebBrowser Control](http://go.microsoft.com/fwlink/?LinkId=198812)