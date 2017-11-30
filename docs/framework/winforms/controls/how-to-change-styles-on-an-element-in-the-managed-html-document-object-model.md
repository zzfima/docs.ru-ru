---
title: "Практическое руководство. Изменение стилей элемента в управляемой объектной модели HTML-документов"
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
helpviewer_keywords: managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 968dd4210e13e301ba2f0ca24617df23706cefc0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a>Практическое руководство. Изменение стилей элемента в управляемой объектной модели HTML-документов
Стили в формате HTML можно использовать для управления внешним видом документа и его элементов. <xref:System.Windows.Forms.HtmlDocument>и <xref:System.Windows.Forms.HtmlElement> поддерживает <xref:System.Windows.Forms.HtmlElement.Style%2A> свойств, которые принимают строки в следующем формате:  
  
 `name1:value1;...;nameN:valueN;`  
  
 Вот `DIV` со строкой стиля, задающей шрифт Arial и весь текст полужирным шрифтом:  
  
 `<DIV style="font-face:arial;font-weight:bold;">`  
  
 `Hello, world!`  
  
 `</DIV>`  
  
 Проблема при управлении стилей с помощью <xref:System.Windows.Forms.HtmlElement.Style%2A> свойство заключается в том, что может оказаться нелегкой задачей Добавление и удаление отдельных параметров стилей из строки. Например, он стал бы сложная процедура для отображение текста курсивом, при наведении курсора на `DIV`и отключение курсивного начертания, когда курсор покидает `DIV`. Времени может возникнуть проблема, если необходимо управлять большим числом стили таким образом.  
  
 Следующая процедура содержит код, который можно использовать, чтобы упростить управление стилями в HTML-документы и элементы. Процедура требует, что вы знаете, как для выполнения основных задач в Windows Forms, такие как создание нового проекта и добавление элемента управления в форму.  
  
### <a name="to-process-style-changes-in-a-windows-forms-application"></a>Для обработки изменений стиля в приложении Windows Forms  
  
1.  Создайте проект Windows Forms.  
  
2.  Создайте новый файл класса, в которых заканчиваются расширением, соответствующим выбранному языку программирования.  
  
3.  Копировать `StyleGenerator` класс в следующем примере в этом разделе в файл класса и сохраните код.  
  
4.  Сохраните следующий HTML-код в файл с именем отнести.  
  
    ```  
    <HTML>  
        <BODY>  
  
            <DIV style="font-face:arial;font-weight:bold;">  
                Hello, world!  
            </DIV><P>  
  
            <DIV>  
                Hello again, world!  
            </DIV><P>  
  
        </BODY>  
    </HTML>  
    ```  
  
5.  Добавить <xref:System.Windows.Forms.WebBrowser> управления с именем `webBrowser1` в главную форму проекта.  
  
6.  Добавьте следующий код в файл кода проекта.  
  
    > [!IMPORTANT]
    >  Убедитесь, что `webBrowser1_DocumentCompleted` обработчика событий настраивается в качестве прослушивателя <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> событий. В [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], дважды щелкните на <xref:System.Windows.Forms.WebBrowser> управления; в текстовом редакторе, настройте прослушиватель программными средствами.  
  
     [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7.  Запустите проект. Наведите курсор на первый `DIV` Обратите внимание на действия кода.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показан полный код для `StyleGenerator` класс, который выполняет синтаксический анализ значение существующего стиля, поддерживает добавление, изменение и удаление стилей и возвращает значение нового стиля с требуемыми изменениями.  
  
 [!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.HtmlElement>
