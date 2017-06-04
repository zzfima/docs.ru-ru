---
title: "Практическое руководство. Изменение стилей элемента в управляемой объектной модели HTML-документов | Microsoft Docs"
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
  - "управляемый HTML DOM, изменение стиля элементов"
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Изменение стилей элемента в управляемой объектной модели HTML-документов
Стили в HTML\-коде можно использовать для управления внешним видом документа и его элементов.  <xref:System.Windows.Forms.HtmlDocument> и <xref:System.Windows.Forms.HtmlElement> поддерживают свойства <xref:System.Windows.Forms.HtmlElement.Style%2A>, принимающие строки стилей в следующем формате:  
  
 `name1:value1;...;nameN:valueN;`  
  
 `DIV` со строкой стиля, задающей шрифт Arial и жирное начертание текста:  
  
 `<DIV style="font-face:arial;font-weight:bold;">`  
  
 `Hello, world!`  
  
 `</DIV>`  
  
 Проблема при управлении стилями при помощи свойства <xref:System.Windows.Forms.HtmlElement.Style%2A> заключается в том, что добавление и удаление отдельных параметров стилей из строки может оказаться нелегкой задачей.  Например, отображение текста курсивом при наведении пользователем курсора на `DIV`, и отключение курсивного начертания, после того как курсор перемещается с `DIV`, может представляет некоторые сложности  Проблема времени может возникнуть при необходимости управления большим количеством стилей подобным образом.  
  
 В следующей процедуре содержится код, который позволит упростить управление стилями в HTML\-документах и элементах.  Для выполнения процедуры требуется знать о выполнении основных задач в Windows Forms, таких как создание нового проекта и добавление элемента управления в форму.  
  
### Обработка изменений стилей в приложении Windows Forms  
  
1.  Создайте новый проект Windows Forms.  
  
2.  Создайте новый файл класса с расширением, соответствующим языку программирования.  
  
3.  Скопируйте код класс `StyleGenerator` из примера в данном разделе в файл класса и сохраните код.  
  
4.  Сохраните следующий HTML\-код в виде файла с именем Test.htm.  
  
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
  
5.  Добавьте элемент управления <xref:System.Windows.Forms.WebBrowser> с именем `webBrowser1` в главную форму проекта.  
  
6.  Добавьте следующий код в файл кода проекта.  
  
    > [!IMPORTANT]
    >  Убедитесь, что обработчик событий `webBrowser1_DocumentCompleted` настроен в качестве прослушивателя для события <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>.  В [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] дважды щелкните элемент управления <xref:System.Windows.Forms.WebBrowser>; настройте прослушиватель программными средствами в текстовом редакторе.  
  
     [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7.  Запустите проект.  Наведите курсор на первый `DIV` и обратите внимание на действия кода.  
  
## Пример  
 Следующий пример кода представляет собой полный код для класса `StyleGenerator`, который разбирает значение существующего стиля, поддерживает добавление, изменение и удаление стилей, и возвращает значение нового стиля с требуемыми изменениями.  
  
 [!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## См. также  
 <xref:System.Windows.Forms.HtmlElement>