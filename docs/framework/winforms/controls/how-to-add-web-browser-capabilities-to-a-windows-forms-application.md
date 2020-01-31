---
title: Добавление возможностей веб-браузера в приложение
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WebBrowser control [Windows Forms], adding Web browser capabilities to your application
- WebBrowser control [Windows Forms], examples
- Web browsers [.NET Framework], adding to Windows Forms
- examples [Windows Forms], WebBrowser control
- Windows Forms, adding Web browser functionality
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
ms.openlocfilehash: 5feecd975700745541103e81fd09bfc5e788c729
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747222"
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a><span data-ttu-id="8ca66-102">Практическое руководство. Добавление функциональности веб-браузера в приложения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8ca66-102">How to: Add Web Browser Capabilities to a Windows Forms Application</span></span>
<span data-ttu-id="8ca66-103">Элемент управления <xref:System.Windows.Forms.WebBrowser> позволяет добавить в приложение функциональность веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="8ca66-103">With the <xref:System.Windows.Forms.WebBrowser> control, you can add Web browser functionality to your application.</span></span> <span data-ttu-id="8ca66-104">По умолчанию он работает как веб-браузер.</span><span class="sxs-lookup"><span data-stu-id="8ca66-104">The control works like a Web browser by default.</span></span> <span data-ttu-id="8ca66-105">После загрузки начального URL-адреса путем установки свойства <xref:System.Windows.Forms.WebBrowser.Url%2A> можно переходить по гиперссылкам, а также совершать переход вперед и назад по истории навигации с помощью сочетаний клавиш.</span><span class="sxs-lookup"><span data-stu-id="8ca66-105">After you load an initial URL by setting the <xref:System.Windows.Forms.WebBrowser.Url%2A> property, you can navigate by clicking hyperlinks or by using keyboard shortcuts to move backward and forward through navigation history.</span></span> <span data-ttu-id="8ca66-106">Дополнительные функциональные возможности браузера по умолчанию доступны в контекстном меню, появляющемся при щелчке правой кнопки мыши.</span><span class="sxs-lookup"><span data-stu-id="8ca66-106">By default, you can access additional browser functionality through the right-click shortcut menu.</span></span> <span data-ttu-id="8ca66-107">Вы также можете открывать новые документы, сбрасывая их в элемент управления.</span><span class="sxs-lookup"><span data-stu-id="8ca66-107">You can also open new documents by dropping them onto the control.</span></span> <span data-ttu-id="8ca66-108">Кроме того, элемент управления <xref:System.Windows.Forms.WebBrowser> имеет несколько свойств, методов и событий, которые можно использовать для реализации возможностей пользовательского интерфейса, аналогичных имеющимся в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8ca66-108">The <xref:System.Windows.Forms.WebBrowser> control also has several properties, methods, and events that you can use to implement user interface features similar to those found in Internet Explorer.</span></span>  
  
 <span data-ttu-id="8ca66-109">В примере кода ниже реализуются адресная строка, стандартные кнопки браузера, меню **Файл**, строка состояния и строка заголовка, в которой содержится заголовок текущей страницы.</span><span class="sxs-lookup"><span data-stu-id="8ca66-109">The following code example implements an address bar, typical browser buttons, a **File** menu, a status bar, and a title bar that displays the current page title.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ca66-110">Пример</span><span class="sxs-lookup"><span data-stu-id="8ca66-110">Example</span></span>  
 [!code-cpp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8ca66-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="8ca66-111">Compiling the Code</span></span>  
 <span data-ttu-id="8ca66-112">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="8ca66-112">This example requires:</span></span>  
  
- <span data-ttu-id="8ca66-113">ссылки на сборки `System`, `System.Drawing` и `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="8ca66-113">References to the `System`, `System.Drawing`, and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ca66-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="8ca66-114">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="8ca66-115">Элемент управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="8ca66-115">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
