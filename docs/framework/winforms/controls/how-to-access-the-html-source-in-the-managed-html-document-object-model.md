---
title: "Практическое руководство. Доступ к исходному коду HTML с использованием управляемой объектной модели документов HTML | Microsoft Docs"
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
  - "HTML, доступ в Windows Forms"
  - "управляемый HTML DOM"
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Доступ к исходному коду HTML с использованием управляемой объектной модели документов HTML
Свойства <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> и <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> в элементе управления <xref:System.Windows.Forms.WebBrowser> возвращают HTML текущего документа в том виде, в котором он существовал при первом отображении.  Если вы измените страницу, используя вызовы таких методов и свойств, как <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> и <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, то при вызове <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> и <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> эти изменения отображаться на будут.  Чтобы получить актуальный HTML\-источник DOM, необходимо вызвать свойство <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> по элементу HTML.  
  
 В следующей процедуре показано, как получить динамический источник и отобразить его в отдельном контекстном меню.  
  
### Получение динамического источника с помощью свойства OuterHtml.  
  
1.  Создайте новое приложение Windows Forms.  Для начала создайте одну форму <xref:System.Windows.Forms.Form> и назовите ее `Form1`.  
  
2.  Создайте элемент управления <xref:System.Windows.Forms.WebBrowser> в приложении Windows Forms и назовите его `WebBrowser1`.  Для получения дополнительной информации см. [Практическое руководство. Добавление функциональности веб\-браузера в приложения Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).  
  
3.  Создайте вторую форму <xref:System.Windows.Forms.Form> с именем `CodeForm`.  
  
4.  Добавьте элемент управления <xref:System.Windows.Forms.RichTextBox> для `CodeForm` и присвойте его свойству <xref:System.Windows.Forms.Control.Dock%2A> значение `Заполнение`.  
  
5.  Создайте в `CodeForm` публичное свойство с именем `Code`.  
  
     [!code-csharp[DisplayWebBrowserCode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  Добавьте элемент управления <xref:System.Windows.Forms.Button> с именем `Button1` в <xref:System.Windows.Forms.Form> и пронаблюдайте за событием <xref:System.Windows.Forms.Control.Click>.  Дополнительные сведения о наблюдении за событиями см. в разделе [События](../../../../docs/standard/events/index.md).  
  
7.  Добавьте в обработчик событий <xref:System.Windows.Forms.Control.Click> следующий код:  
  
     [!code-csharp[DisplayWebBrowserCode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## Отказоустойчивость  
 Всегда тестируйте значение <xref:System.Windows.Forms.WebBrowser.Document%2A>, прежде чем пытаться его извлечь.  Если текущая страница не закончила загружаться, значит, <xref:System.Windows.Forms.WebBrowser.Document%2A> либо один или несколько дочерних объектов еще не инициализированы.  
  
## См. также  
 [Использование управляемой объектной модели HTML\-документов](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)   
 [Общие сведения об элементе управления WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)