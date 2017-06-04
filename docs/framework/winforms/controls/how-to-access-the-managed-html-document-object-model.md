---
title: "Практическое руководство. Доступ к управляемой объектной модели HTML-документов | Microsoft Docs"
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
  - "Модели DOM HTML, доступ к"
  - "управляемый HTML DOM, доступ к"
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Доступ к управляемой объектной модели HTML-документов
Получить доступ к управляемой объектной модели HTML-документа (DOM) можно из двух типов приложений.  
  
-   Приложение Windows Forms (.exe), в котором размещен управляемый <xref:System.Windows.Forms.WebBrowser> элемента управления. Эти две технологии дополняют друг друга, с <xref:System.Windows.Forms.WebBrowser> управления отображением страницы пользователю, а HTML DOM представляет логическую структуру документа.  
  
-   Windows Forms <xref:System.Windows.Forms.UserControl> размещается в Internet Explorer. HTML DOM представляет страницу, где можно получить доступ к вашей <xref:System.Windows.Forms.UserControl> размещается для изменения структуры документа, открытия модальных диалоговых окон, а множество других возможностей.  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a>Доступ к DOM из приложения Windows Forms  
  
1.  Узел <xref:System.Windows.Forms.WebBrowser> управления в приложении Windows Forms и наблюдайте за <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> событий. Сведения о размещении элементов управления и отслеживании событий см. в разделе [события](../../../../docs/standard/events/index.md).  
  
2.  Получить <xref:System.Windows.Forms.HtmlDocument> для текущей страницы, открыв <xref:System.Windows.Forms.WebBrowser.Document%2A> свойство <xref:System.Windows.Forms.WebBrowser> элемента управления.  
  
<!-- TODO: review snippet reference  [!CODE [AccessHTMLDOMApp#1](AccessHTMLDOMApp#1)]  -->  
  
### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a>Доступ к DOM из элемента управления UserControl, размещенного в Internet Explorer  
  
1.  Создать собственный пользовательский производный класс класса <xref:System.Windows.Forms.UserControl> класса. Дополнительные сведения см. в разделе [как: составные элементы управления автора](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md).  
  
2.  Поместите следующий код в обработчик событий загрузки для вашей <xref:System.Windows.Forms.UserControl>:  
  
 [!code-csharp[AccessHTMLDOMControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
  
1.  При использовании DOM через <xref:System.Windows.Forms.WebBrowser> управления, необходимо подождать, пока не <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> событие возникает перед попыткой обращения к <xref:System.Windows.Forms.WebBrowser.Document%2A> свойство <xref:System.Windows.Forms.WebBrowser> элемента управления. <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> событие возникает после загрузки всего документа, если использовать DOM до того, существует риск возникновения исключения во время выполнения приложения.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
  
1.  Приложение или <xref:System.Windows.Forms.UserControl> потребуется полное доверие, чтобы получить доступ к управляемую модель HTML DOM. При развертывании приложения Windows Forms с помощью [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], вы можете запросить полное доверие, используя повышение уровня разрешений или развертывания надежных приложений; см. раздел [защита приложений ClickOnce](../Topic/Securing%20ClickOnce%20Applications.md) подробные сведения.  
  
## <a name="see-also"></a>См. также  
 [Использование объектной модели управляемого HTML-документа](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)