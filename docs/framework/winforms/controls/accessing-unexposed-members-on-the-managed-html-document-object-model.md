---
title: "Доступ к членам управляемой объектной модели документов HTML, доступ к которым не предоставляется явно | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "управляемый HTML DOM, получения доступа к членам, не предоставленным явно"
  - "члены, не предоставленные явно"
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Доступ к членам управляемой объектной модели документов HTML, доступ к которым не предоставляется явно
Управляемая объектная модель \(DOM\) HTML\-документов содержит класс с именем <xref:System.Windows.Forms.HtmlElement>, предоставляющий свойства, методы и события, общие для всех элементов HTML.  Иногда, однако, требуется доступ к членам, которые управляемый интерфейс не предоставляет непосредственно.  В этом разделе рассматриваются два способа получения доступа к членам, не предоставленным явно, включая [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] и функции языка сценариев VBScript, определенные внутри веб\-страницы.  
  
## Доступ с помощью управляемых интерфейсов к членам, не предоставленным явно  
 <xref:System.Windows.Forms.HtmlDocument> и <xref:System.Windows.Forms.HtmlElement> предоставляют четыре метода обеспечения доступа к членам, не предоставленным явно.  В следующей таблице приведены типы и соответствующие методы.  
  
|Тип члена|Методы|  
|---------------|------------|  
|Свойства \(<xref:System.Windows.Forms.HtmlElement>\)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|Методы|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|События \(<xref:System.Windows.Forms.HtmlDocument>\)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|События \(<xref:System.Windows.Forms.HtmlElement>\)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|События \(<xref:System.Windows.Forms.HtmlWindow>\)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 При использовании этих методов предполагается, что имеется элемент правильного базового типа.  Предположим, что требуется ожидать передачи данных от события `Submit` элемента `FORM` на HTML\-странице, чтобы выполнить предварительную обработку значений `FORM` перед их отправкой на сервер.  В идеальном случае, если имеется возможность управления HTML\-кодом, можно задать для `FORM` уникальный атрибут `ID`.  
  
```  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 После загрузки этой страницы в элемент управления <xref:System.Windows.Forms.WebBrowser> метод <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> можно использовать для извлечения `FORM` во время выполнения с помощью формы `form1` в качестве аргумента.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## Доступ к неуправляемым интерфейсам  
 Доступ к членам управляемой модели HTML DOM, не предоставляемым явно, также можно получить с помощью интерфейса неуправляемой модели COM, предоставляемого каждым классом DOM.  Этот способ рекомендуется, если требуется выполнить несколько вызовов членов, не предоставленных явно, или если члены, не предоставленные явно, возвращают неуправляемые интерфейсы, не упакованные в управляемую модель HTML DOM.  
  
 В следующей таблице приведены все неуправляемые интерфейсы, предоставляемые через управляемую модель HTML DOM.  Чтобы получить описание использования и пример кода, щелкните соответствующую ссылку.  
  
|Тип|Неуправляемый интерфейс|  
|---------|-----------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 Самый простой способ \- использовать интерфейсы модели COM добавить ссылку на неуправляемую библиотеку HTML DOM \(MSHTML.dll\) из приложения, хотя это не поддерживается.  Дополнительные сведения см. в разделе [Статья 934368 базы знаний Майкрософт](http://support.microsoft.com/kb/934368).  
  
## Функции доступа к скрипту  
 HTML\-страница может определять одну или несколько функций с помощью скриптового языка, такого как [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] или VBScript.  Эти функции размещаются внутри страницы `SCRIPT` на странице и могут выполняться по запросу или в ответ на событие в модели DOM.  
  
 Используя метод <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>, можно вызвать любую функцию скрипта, определенную в HTML\-странице.  Если метод скрипта возвращает элемент HTML, можно использовать приведение, чтобы преобразовать этот возвращаемый результат в <xref:System.Windows.Forms.HtmlElement>.  Дополнительные сведения и пример кода содержатся в разделе <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.  
  
## См. также  
 [Использование управляемой объектной модели HTML\-документов](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)