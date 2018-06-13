---
title: Общие сведения об элементе управления WebBrowser
ms.date: 03/30/2017
f1_keywords:
- WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
ms.openlocfilehash: 2e69b71b3e354101d950d6f7011b13fc7c0de030
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540996"
---
# <a name="webbrowser-control-overview"></a>Общие сведения об элементе управления WebBrowser
<xref:System.Windows.Forms.WebBrowser> Управления предоставляет управляемую оболочку для элемента управления WebBrowser ActiveX. Управляемая оболочка позволяет отображать веб-страницы в клиентских приложениях Windows Forms. Можно использовать <xref:System.Windows.Forms.WebBrowser> управления дублировать возможности просмотра веб-обозревателя в приложении, либо можно отключить функциональные возможности Internet Explorer по умолчанию и использовать элемент управления в качестве простого просмотра документа HTML. Также можно использовать элемент управления для добавления в форму элементов интерфейса пользователя на основе DHTML и скрыть тот факт, что они размещаются в <xref:System.Windows.Forms.WebBrowser> элемента управления. Такой подход позволяет легко объединить веб-элементов управления с помощью элементов управления Windows Forms в одном приложении.  
  
## <a name="frequently-used-properties-methods-and-events"></a>Часто используемые свойства, методы и события  
 <xref:System.Windows.Forms.WebBrowser> Элемент управления имеет несколько свойств, методов и событий, которые можно использовать для реализации элементов управления в Internet Explorer. Например, можно использовать `Navigate` метод, реализуемый в адресной строке и `GoBack`, `GoForward`, `Stop`, и `Refresh` методы для реализации кнопки навигации на панели инструментов. Можно обработать `Navigated` событий для обновления адресную строку со значением `Url` свойство и в заголовке, со значением `DocumentTitle` свойство.  
  
 Если вы хотите создать содержимое страницы в приложении, можно задать `DocumentText` свойства. Если вы знакомы с HTML объектной модели документа (DOM), можно управлять содержимое текущей веб-страницы через `Document` свойство. Это свойство можно хранить и изменять документы в памяти вместо операций с файлами.  
  
 `Document` Свойство также можно вызывать методы, реализованные в скрипта кода из кода клиентского приложения веб-страницы. Для доступа к коду клиентского приложения из кода сценария, установите `ObjectForScripting` свойство. Объект, который указывается может осуществляться код скрипта как `window.external` объект.  
  
|name|Описание|  
|----------|-----------------|  
|Свойство <xref:System.Windows.Forms.WebBrowser.Document%2A>|Возвращает объект, который обеспечивает управляемый доступ к модели объекта документа HTML DOM текущей веб-страницы.|  
|Событие <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>|Происходит по завершении загрузки веб-страницы.|  
|Свойство <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>|Возвращает или задает HTML-содержимое текущей веб-страницы.|  
|Свойство <xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A>|Возвращает заголовок текущей страницы.|  
|Метод <xref:System.Windows.Forms.WebBrowser.GoBack%2A>|Переход на предыдущую страницу в журнале.|  
|Метод <xref:System.Windows.Forms.WebBrowser.GoForward%2A>|Переходит на следующую страницу в журнале.|  
|Метод <xref:System.Windows.Forms.WebBrowser.Navigate%2A>|Переходит к указанному URL-АДРЕСУ.|  
|Событие <xref:System.Windows.Forms.WebBrowser.Navigating>|Происходит перед выполнением перехода, что позволяет отменить действие.|  
|Свойство <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>|Возвращает или задает объект, который кодом скрипта веб-страницы можно использовать для взаимодействия с приложением.|  
|Метод <xref:System.Windows.Forms.WebBrowser.Print%2A>|Печать текущей страницы.|  
|Метод <xref:System.Windows.Forms.WebBrowser.Refresh%2A>|Перезагружает текущую страницу Web.|  
|Метод <xref:System.Windows.Forms.WebBrowser.Stop%2A>|Прерывает текущую операцию перехода и останавливает динамические элементы страниц звуки и анимации.|  
|Свойство <xref:System.Windows.Forms.WebBrowser.Url%2A>|Возвращает или задает URL-адрес текущей веб-страницы. Задание этого свойства переход на новый URL-адрес элемента управления.|  
  
## <a name="see-also"></a>См. также  
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
 [Практическое руководство. Переход по заданному URL-адресу с помощью элемента управления WebBrowser](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [Практическое руководство. Печать с использованием элемента управления WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)  
 [Практическое руководство. Добавление функциональности веб-браузера в приложения Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)  
 [Практическое руководство. Создание средства просмотра HTML-документов в приложении Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)  
 [Практическое руководство. Реализация двунаправленного взаимодействия между кодом DHTML и клиентским кодом приложений](../../../../docs/framework/winforms/controls/implement-two-way-com-between-dhtml-and-client.md)  
 [Безопасность элемента управления WebBrowser](../../../../docs/framework/winforms/controls/webbrowser-security.md)
