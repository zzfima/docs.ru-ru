---
title: "Общие сведения об элементе управления WebBrowser | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WebBrowser"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "веб-страницы, отображение в приложениях"
  - "WebBrowser - элемент управления [Windows Forms], сведения"
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Общие сведения об элементе управления WebBrowser
Элемент управления <xref:System.Windows.Forms.WebBrowser> предоставляет управляемую оболочку для элемента управления ActiveX WebBrowser.  Управляемая оболочка позволяет отображать веб\-страницы в клиентских приложениях Windows Forms.  С помощью элемента управления <xref:System.Windows.Forms.WebBrowser> можно воспроизвести в приложении функциональность веб\-обозревателя Internet Explorer, либо можно отключить функциональность Internet Explorer, заданную по умолчанию, и использовать этот элемент управления в качестве простого средства просмотра HTML\-документов.  Данный элемент управления может также использоваться для добавления на форму DHTML\-элементов пользовательского интерфейса, причем факт их размещения в элементе управления <xref:System.Windows.Forms.WebBrowser> будет незаметен.  Такой подход позволяет эффективно сочетать использование веб\-элементов управления и элементов управления Windows Forms в рамках одного приложения.  
  
## Часто используемые свойства, методы и события  
 Элемент управления <xref:System.Windows.Forms.WebBrowser> имеет ряд свойств, методов и событий, которые могут использоваться для реализации элементов управления Internet Explorer.  Например, метод `Navigate` можно использовать для реализации адресной строки, а методы `GoBack`, `GoForward`, `Stop` и `Refresh` — для реализации кнопок перехода в панели инструментов.  Путем обработки события `Navigated` может производиться обновление адресной строки значением свойства `Url`, а строки заголовка — значением свойства `DocumentTitle`.  
  
 Создать содержание страницы в приложении можно путем задания значения свойства `DocumentText`.   При наличии опыта работы с объектной моделью HTML\-документов \(DOM\) содержимым текущей веб\-страницы можно управлять с помощью свойства `Document`.  Благодаря этому свойству можно хранить и изменять документы в памяти вместо операций с файлами.  
  
 Свойство `Document` также позволяет обращаться к методам, реализованным в коде скрипта веб\-страницы, из кода клиентского приложения.  Для доступа к коду клиентского приложения из кода скрипта следует задать значение свойства `ObjectForScripting`.  Доступ к указанному объекту из кода скрипта может осуществляться как к объекту `window.external`.  
  
|Имя|Описание|  
|---------|--------------|  
|Свойство <xref:System.Windows.Forms.WebBrowser.Document%2A>|Возвращает объект, обеспечивающий управляемый доступ к объектной модели HTML\-документа \(DOM\) для текущей веб\-страницы.|  
|Событие <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>|Наступает по завершении загрузки веб\-страницы.|  
|Свойство <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>|Получает или задает HTML\-содержимое текущей веб\-страницы.|  
|Свойство <xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A>|Возвращает заголовок текущей веб\-страницы.|  
|Метод <xref:System.Windows.Forms.WebBrowser.GoBack%2A>|Переход к предыдущей странице согласно хронологии.|  
|Метод <xref:System.Windows.Forms.WebBrowser.GoForward%2A>|Переход к следующей странице согласно хронологии.|  
|Метод <xref:System.Windows.Forms.WebBrowser.Navigate%2A>|Переход по указанному URL\-адресу.|  
|Событие <xref:System.Windows.Forms.WebBrowser.Navigating>|Наступает перед выполнением перехода, что позволяет отменить действие.|  
|Свойство <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>|Получает или задает объект, который может использоваться кодом скрипта веб\-страницы для взаимодействия с приложением.|  
|Метод <xref:System.Windows.Forms.WebBrowser.Print%2A>|Печать текущей веб\-страницы.|  
|Метод <xref:System.Windows.Forms.WebBrowser.Refresh%2A>|Перезагрузка текущей веб\-страницы.|  
|Метод <xref:System.Windows.Forms.WebBrowser.Stop%2A>|Прерывает текущую операцию перехода и останавливает работу динамических элементов страницы, таких как звук и анимация.|  
|Свойство <xref:System.Windows.Forms.WebBrowser.Url%2A>|Получает или задает URL\-адрес текущей веб\-страницы.  При установке значения этого свойства, элемент управления переходит к новому URL\-адресу.|  
  
## См. также  
 <xref:System.Windows.Forms.WebBrowser>   
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventArgs>   
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventHandler>   
 <xref:System.Windows.Forms.WebBrowserEncryptionLevel>   
 <xref:System.Windows.Forms.WebBrowserNavigatedEventArgs>   
 <xref:System.Windows.Forms.WebBrowserNavigatedEventHandler>   
 <xref:System.Windows.Forms.WebBrowserNavigatingEventArgs>   
 <xref:System.Windows.Forms.WebBrowserNavigatingEventHandler>   
 <xref:System.Windows.Forms.WebBrowserProgressChangedEventArgs>   
 <xref:System.Windows.Forms.WebBrowserReadyState>   
 <xref:System.Windows.Forms.WebBrowserRefreshOption>   
 [Практическое руководство. Переход по заданному URL с помощью элемента управления WebBrowser](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)   
 [Практическое руководство. Печать с использованием элемента управления WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)   
 [Практическое руководство. Добавление функциональности веб\-браузера в приложения Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)   
 [Практическое руководство. Создание средства просмотра HTML\-документов в приложении Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)   
 [Практическое руководство. Реализация двунаправленного взаимодействия между кодом DHTML и клиентским кодом приложений](../../../../docs/framework/winforms/controls/implement-two-way-com-between-dhtml-and-client.md)   
 [Безопасность элемента управления WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-security.md)