---
title: Доступ к членам управляемой объектной модели документов HTML, доступ к которым не предоставляется явно
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: d2fbccfb3ecd7716420ca951e86f728798d25258
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526437"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a>Доступ к членам управляемой объектной модели документов HTML, доступ к которым не предоставляется явно
Управляемый объектной модели (DOM) HTML документа содержит класс с именем <xref:System.Windows.Forms.HtmlElement> , предоставляющий свойства, методы и события, общие для всех элементов HTML. Иногда тем не менее, необходимо будет получить доступ к членам, которые управляемый интерфейс не предоставляет непосредственно. В этом разделе рассматриваются два способа получения доступа к членам, не предоставленным явно, включая [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] и функции VBScript, определенные внутри веб-страницы.  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a>Доступ к членам, не предоставленным явно через управляемых интерфейсов  
 <xref:System.Windows.Forms.HtmlDocument> и <xref:System.Windows.Forms.HtmlElement> предоставляют четыре метода, которые обеспечивают доступ к членам, не предоставленным явно. В следующей таблице показаны типы и соответствующие методы.  
  
|Тип члена|Методы|  
|-----------------|-----------------|  
|Свойства (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|Методы|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|События (<xref:System.Windows.Forms.HtmlDocument>)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|События (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|События (<xref:System.Windows.Forms.HtmlWindow>)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 При использовании этих методов, предполагается, что имеется элемент правильного базового типа. Предположим, что необходимо прослушивать `Submit` событие `FORM` на HTML-странице, чтобы выполнить предварительную обработку `FORM`его значения перед их отправкой на сервер. В идеальном случае, если контроль над HTML, необходимо определить `FORM` уникальный `ID` атрибута.  
  
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
  
 После загрузки этой страницы в <xref:System.Windows.Forms.WebBrowser> управления, можно использовать <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> метод для извлечения `FORM` во время выполнения с помощью `form1` в качестве аргумента.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a>Доступ к неуправляемым интерфейсам  
 Также доступа к членам, не предоставленным явно на управляемый HTML DOM, используя неуправляемые интерфейсы объектов модели компонентов (COM), предоставляемые каждым классом DOM. Это рекомендуется, если необходимо выполнить несколько вызовов членов, не предоставленные явно или члены, не предоставленные явно возвращают неуправляемые интерфейсы, не упакованные управляемую модель HTML DOM.  
  
 В следующей таблице приведены все неуправляемые интерфейсы, предоставляемые через управляемую модель HTML DOM. Щелкните ссылку для пояснения ее использования и пример кода.  
  
|Тип|Неуправляемый интерфейс|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 Самый простой способ использования интерфейсов COM является добавление ссылки на неуправляемую библиотеку HTML DOM (MSHTML.dll) из своего приложения, несмотря на то, что это не поддерживается. Дополнительные сведения см. в разделе [934368 статьи базы знаний](http://support.microsoft.com/kb/934368).  
  
## <a name="accessing-script-functions"></a>Доступ к функциям скриптов  
 HTML-страницы можно определить одну или несколько функций с помощью языка сценариев, таких как [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] или VBScript. Эти функции размещаются внутри `SCRIPT` страницы на странице и могут выполняться по запросу или в ответ на событие в модели DOM.  
  
 Можно вызвать любую функцию скрипта, определяется в HTML-страницы с использованием <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> метод. Если метод скрипта возвращает HTML-элемент, можно использовать приведение, чтобы преобразовать этот возвращаемый результат <xref:System.Windows.Forms.HtmlElement>. Дополнительные сведения и пример кода см. в разделе <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.  
  
## <a name="see-also"></a>См. также  
 [Использование управляемой объектной модели HTML-документов](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
