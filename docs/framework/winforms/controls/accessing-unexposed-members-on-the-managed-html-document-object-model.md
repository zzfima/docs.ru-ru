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
ms.openlocfilehash: 525ef52ecbbc61fba787fa8286c56c638d837faf
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988401"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a>Доступ к членам управляемой объектной модели документов HTML, доступ к которым не предоставляется явно
Управляемый HTML-модель DOM (DOM) содержит класс с <xref:System.Windows.Forms.HtmlElement> именем, который предоставляет свойства, методы и события, общие для всех элементов HTML. Тем не менее иногда требуется доступ к членам, которые управляемый интерфейс не предоставляет напрямую. В этом разделе рассматриваются два способа доступа к неоткрытым членам, в том числе функции JScript и VBScript, определенные в веб-странице.  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a>Доступ к неоткрытым членам через управляемые интерфейсы  
 <xref:System.Windows.Forms.HtmlDocument>и <xref:System.Windows.Forms.HtmlElement> предоставляют четыре метода, которые обеспечивают доступ к неоткрытым членам. В следующей таблице показаны типы и соответствующие им методы.  
  
|Тип члена|Метод (ы)|  
|-----------------|-----------------|  
|Свойства (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|Методы|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|События (<xref:System.Windows.Forms.HtmlDocument>)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|События (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|События (<xref:System.Windows.Forms.HtmlWindow>)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 При использовании этих методов предполагается, что у вас есть элемент правильного базового типа. Предположим, что необходимо прослушивать `Submit` событие `FORM` элемента на HTML-странице, чтобы можно было выполнить `FORM`предварительную обработку значений до того, как пользователь отправит их на сервер. В идеале, если вы управляете HTML, определите `FORM` для атрибута значение Unique. `ID`  
  
```html  
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
  
 После <xref:System.Windows.Forms.WebBrowser> загрузки этой страницы в элемент управления можно <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> использовать метод для получения `FORM` во время выполнения, используя `form1` в качестве аргумента.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a>Доступ к неуправляемым интерфейсам  
 Вы также можете получить доступ к неоткрытым членам управляемой модели HTML DOM с помощью неуправляемых интерфейсов COM, предоставляемых каждым классом DOM. Это рекомендуется делать, если необходимо выполнить несколько вызовов для невидимых членов или если непредоставленные члены возвращают другие неуправляемые интерфейсы, не инкапсулированные управляемой моделью HTML DOM.  
  
 В следующей таблице показаны все неуправляемые интерфейсы, предоставляемые через управляемую модель DOM HTML. Щелкните каждую ссылку, чтобы получить объяснение его использования и пример кода.  
  
|Тип|Неуправляемый интерфейс|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 Самый простой способ использования интерфейсов COM — добавить ссылку на неуправляемую библиотеку DOM HTML (MSHTML. dll) из приложения, хотя это не поддерживается. Дополнительные сведения см. в [статье базы знаний 934368](https://support.microsoft.com/kb/934368).  
  
## <a name="accessing-script-functions"></a>Доступ к функциям скрипта  
 HTML-страница может определять одну или несколько функций с помощью языка сценариев, такого как JScript или VBScript. Эти функции помещаются внутри `SCRIPT` страницы страницы и могут выполняться по требованию или в ответ на событие в модели DOM.  
  
 Вы можете вызывать любые функции скриптов, определенные на HTML-странице, с <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> помощью метода. Если метод скрипта возвращает HTML-элемент, можно использовать приведение для преобразования возвращаемого результата в <xref:System.Windows.Forms.HtmlElement>. Дополнительные сведения и примеры кода см. <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>в разделе.  
  
## <a name="see-also"></a>См. также

- [Использование управляемой объектной модели HTML-документов](using-the-managed-html-document-object-model.md)
