---
title: Создание средства просмотра HTML-документов в приложении Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 913bc86af034645b4b8cf3d69da4c9def58fc19c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732848"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>Практическое руководство. Создание средства просмотра HTML-документов в приложении Windows Forms
Можно использовать элемент управления <xref:System.Windows.Forms.WebBrowser> для отображения и печати HTML-документов, не предоставляя полный набор функций браузера Интернета. Это полезно, если вы хотите использовать возможности форматирования HTML, но не хотите, чтобы пользователи загружали произвольные веб-страницы, которые могут содержать ненадежные веб-элементы управления или потенциально вредоносный код скрипта. Может потребоваться ограничить возможности элемента управления <xref:System.Windows.Forms.WebBrowser> таким образом, например, чтобы использовать его в качестве средства просмотра электронной почты HTML или для предоставления в приложении справки в формате HTML.  
  
### <a name="to-create-an-html-document-viewer"></a>Создание средства просмотра HTML-документов  
  
1. Задайте для свойства <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> значение `false`, чтобы элемент управления <xref:System.Windows.Forms.WebBrowser> не открывал файлы.  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. Задайте для свойства <xref:System.Windows.Forms.WebBrowser.Url%2A> расположение исходного файла для вывода.  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- элемент управления <xref:System.Windows.Forms.WebBrowser> с именем `webBrowser1`;  
  
- ссылки на сборки `System` и `System.Windows.Forms`.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [Общие сведения об элементе управления WebBrowser](webbrowser-control-overview.md)
- [Безопасность элемента управления WebBrowser](webbrowser-security.md)
- [Практическое руководство. Переход по заданному URL-адресу с помощью элемента управления WebBrowser](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [Практическое руководство. Печать с использованием элемента управления WebBrowser](how-to-print-with-a-webbrowser-control.md)
