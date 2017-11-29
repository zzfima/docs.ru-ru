---
title: "Практическое руководство. Доступ к исходному коду HTML с использованием управляемой объектной модели документов HTML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7ef9839029e1c60cbc0d713e8982baa5708a281f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a>Практическое руководство. Доступ к исходному коду HTML с использованием управляемой объектной модели документов HTML
Свойства <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> и <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> в элементе управления <xref:System.Windows.Forms.WebBrowser> возвращают HTML текущего документа в том виде, в котором он существовал при первом отображении. Если вы измените страницу, используя вызовы таких методов и свойств, как <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> и <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, то при вызове <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> и <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> эти изменения отображаться на будут. Чтобы получить актуальный HTML-источник DOM, необходимо вызвать свойство <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> по элементу HTML.  
  
 В следующей процедуре показано, как получить динамический источник и отобразить его в отдельном контекстном меню.  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a>Получение динамического источника с помощью свойства OuterHtml.  
  
1.  Создайте новое приложение Windows Forms. Создайте одну <xref:System.Windows.Forms.Form>и назовите его `Form1`.  
  
2.  Узел <xref:System.Windows.Forms.WebBrowser> элемент управления в приложении Windows Forms и назовите его `WebBrowser1`. Дополнительные сведения см. в разделе [как: Добавление функциональности веб-браузера в приложении Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).  
  
3.  Создайте вторую <xref:System.Windows.Forms.Form> с именем `CodeForm`.  
  
4.  Добавить <xref:System.Windows.Forms.RichTextBox> управления `CodeForm` и задайте его <xref:System.Windows.Forms.Control.Dock%2A> свойства `Fill`.  
  
5.  Создайте открытое свойство на `CodeForm` вызывается `Code`.  
  
     [!code-csharp[DisplayWebBrowserCode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  Добавить <xref:System.Windows.Forms.Button> управления с именем `Button1` для вашей <xref:System.Windows.Forms.Form>и наблюдайте за <xref:System.Windows.Forms.Control.Click> событий. Дополнительные сведения об отслеживании событий см. в разделе [события](../../../../docs/standard/events/index.md).  
  
7.  Добавьте следующий код в обработчик событий <xref:System.Windows.Forms.Control.Click>.  
  
     [!code-csharp[DisplayWebBrowserCode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Всегда тестируйте значение <xref:System.Windows.Forms.WebBrowser.Document%2A>, прежде чем пытаться его извлечь. Если текущая страница не закончила загружаться, значит, <xref:System.Windows.Forms.WebBrowser.Document%2A> либо один или несколько дочерних объектов еще не инициализированы.  
  
## <a name="see-also"></a>См. также  
 [Использование управляемой объектной модели HTML-документов](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)  
 [Общие сведения об элементе управления WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)
