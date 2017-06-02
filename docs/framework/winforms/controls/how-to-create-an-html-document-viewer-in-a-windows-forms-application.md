---
title: "Практическое руководство. Создание средства просмотра HTML-документов в приложении Windows Forms | Microsoft Docs"
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
  - "средства просмотра документов"
  - "WebBrowser - элемент управления [Windows Forms], создание средства просмотра документа HTML"
  - "Windows Forms, создание средств просмотра документов"
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Создание средства просмотра HTML-документов в приложении Windows Forms
Элемент управления <xref:System.Windows.Forms.WebBrowser> может использоваться как средство для отображения и печати HTML\-документов с ограниченными возможностями веб\-браузера.  Это может оказаться полезным в том случае, если необходимо воспользоваться возможностями форматирования HTML, ограничив в то же время доступ пользователей к произвольным веб\-страницам, которые могут содержать небезопасные веб\-элементы управления или потенциально вредоносный код скрипта.  Подобное ограничение возможностей элемента управления <xref:System.Windows.Forms.WebBrowser> может быть необходимым, например, при его использовании в качестве средства просмотра электронной почты либо при организации справочной системы приложения в формате HTML.  
  
### Создание средства просмотра HTML\-документов  
  
1.  Установите для свойства <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> значение `false`, чтобы элемент управления <xref:System.Windows.Forms.WebBrowser> не мог открывать файлы, перетаскиваемые на его поверхность.  
  
     [!code-csharp[WebBrowserMisc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  В качестве значения свойства <xref:System.Windows.Forms.WebBrowser.Url%2A> укажите размещение первого отображаемого файла.  
  
     [!code-csharp[WebBrowserMisc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Элемент управления <xref:System.Windows.Forms.WebBrowser> с именем `webBrowser1`.  
  
-   Ссылки на сборки `System` и `System.Windows.Forms`.  
  
## См. также  
 <xref:System.Windows.Forms.WebBrowser>   
 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>   
 <xref:System.Windows.Forms.WebBrowser.Url%2A>   
 [Общие сведения об элементе управления WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)   
 [Безопасность элемента управления WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-security.md)   
 [Практическое руководство. Переход по заданному URL с помощью элемента управления WebBrowser](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)   
 [Практическое руководство. Печать с использованием элемента управления WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)