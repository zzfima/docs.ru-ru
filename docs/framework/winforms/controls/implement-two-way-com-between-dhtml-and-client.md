---
title: Практическое руководство. Реализация двунаправленного взаимодействия между кодом DHTML и клиентским кодом приложений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.ObjectForScripting
- WebBrowser.Document
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- communications [Windows Forms], DHTML and client applications
- examples [Windows Forms], WebBrowser control
- WebBrowser control [Windows Forms], communication between DHTML and client application
- DHTML [Windows Forms], embedding in Windows Forms
ms.assetid: 55353a32-b09e-4479-a521-ff3a5ff9a708
ms.openlocfilehash: 52928b11ce3577a1fb6d218b4a74b986f5fe8d1e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710268"
---
# <a name="how-to-implement-two-way-communication-between-dhtml-code-and-client-application-code"></a><span data-ttu-id="84370-102">Практическое руководство. Реализация двунаправленного взаимодействия между кодом DHTML и клиентским кодом приложений</span><span class="sxs-lookup"><span data-stu-id="84370-102">How to: Implement Two-Way Communication Between DHTML Code and Client Application Code</span></span>
<span data-ttu-id="84370-103">Элемент управления <xref:System.Windows.Forms.WebBrowser> можно использовать для добавления существующего динамического кода веб-приложений HTML (DHTML) в клиентские приложения Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="84370-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to add existing dynamic HTML (DHTML) Web application code to your Windows Forms client applications.</span></span> <span data-ttu-id="84370-104">Это полезно, если на разработку элементов управления DHTML затрачено немало времени и нужно воспользоваться широкими возможностями интерфейса Windows Forms, не тратя время на переписывание существующего кода.</span><span class="sxs-lookup"><span data-stu-id="84370-104">This is useful when you have invested significant development time in creating DHTML-based controls and you want to take advantage of the rich user interface capabilities of Windows Forms without having to rewrite existing code.</span></span>  
  
 <span data-ttu-id="84370-105">Элемент управления <xref:System.Windows.Forms.WebBrowser> позволяет реализовать двусторонний обмен данными между кодом клиентского приложения и кодом скрипта веб-страницы с помощью свойств <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> и <xref:System.Windows.Forms.WebBrowser.Document%2A>.</span><span class="sxs-lookup"><span data-stu-id="84370-105">The <xref:System.Windows.Forms.WebBrowser> control lets you implement two-way communication between your client application code and your Web page scripting code through the <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> and <xref:System.Windows.Forms.WebBrowser.Document%2A> properties.</span></span> <span data-ttu-id="84370-106">Кроме того, вы можете настроить элемент управления <xref:System.Windows.Forms.WebBrowser> так, чтобы веб-элементы управления выглядели точно так же, как другие элементы управления в форме приложения, то есть чтобы скрыть их реализацию посредством DHTML.</span><span class="sxs-lookup"><span data-stu-id="84370-106">Additionally, you can configure the <xref:System.Windows.Forms.WebBrowser> control so that your Web controls blend seamlessly with other controls on your application form, hiding their DHTML implementation.</span></span> <span data-ttu-id="84370-107">Для одновременного использования элементов управления следует отформатировать страницу так, чтобы ее фоновый цвет и стиль оформления соответствовали остальной форме, и использовать свойства <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>, <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> и <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> для отключения стандартных функций браузера.</span><span class="sxs-lookup"><span data-stu-id="84370-107">To seamlessly blend the controls, format the page displayed so that its background color and visual style match the rest of the form, and use the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>, <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>, and <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> properties to disable standard browser features.</span></span>  
  
### <a name="to-embed-dhtml-in-your-windows-forms-application"></a><span data-ttu-id="84370-108">Внедрение DHTML в приложение Windows Forms</span><span class="sxs-lookup"><span data-stu-id="84370-108">To embed DHTML in your Windows Forms application</span></span>  
  
1.  <span data-ttu-id="84370-109">Присвойте свойству <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> элемента управления <xref:System.Windows.Forms.WebBrowser> значение `false`, чтобы элемент управления <xref:System.Windows.Forms.WebBrowser> не открывал файлы, которые перетаскиваются в него мышью.</span><span class="sxs-lookup"><span data-stu-id="84370-109">Set the <xref:System.Windows.Forms.WebBrowser> control's <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#1)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#1)]  
  
2.  <span data-ttu-id="84370-110">Присвойте свойству <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> значение `false`, чтобы элемент управления <xref:System.Windows.Forms.WebBrowser> не выводил контекстное меню при щелчке правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="84370-110">Set the control's <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from displaying its shortcut menu when the user right-clicks it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#2)]  
  
3.  <span data-ttu-id="84370-111">Присвойте свойству <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> значение `false`, чтобы элемент управления <xref:System.Windows.Forms.WebBrowser> не отвечал на нажатие сочетаний клавиш.</span><span class="sxs-lookup"><span data-stu-id="84370-111">Set the control's <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from responding to shortcut keys.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#3)]  
  
4.  <span data-ttu-id="84370-112">Задайте свойство <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> в конструкторе формы или в обработчике событий <xref:System.Windows.Forms.Form.Load>.</span><span class="sxs-lookup"><span data-stu-id="84370-112">Set the <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> property in the form's constructor or a <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
     <span data-ttu-id="84370-113">В приведенном ниже коде для объекта скрипта используется класс формы.</span><span class="sxs-lookup"><span data-stu-id="84370-113">The following code uses the form class itself for the scripting object.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="84370-114">Модель COM должна иметь доступ к объекту скрипта.</span><span class="sxs-lookup"><span data-stu-id="84370-114">Component Object Model (COM) must be able to access the scripting object.</span></span> <span data-ttu-id="84370-115">Чтобы сделать форму доступной для COM, добавьте в класс формы атрибут <xref:System.Runtime.InteropServices.ComVisibleAttribute>.</span><span class="sxs-lookup"><span data-stu-id="84370-115">To make your form visible to COM, add the <xref:System.Runtime.InteropServices.ComVisibleAttribute> attribute to your form class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#4)]  
  
5.  <span data-ttu-id="84370-116">Реализуйте в коде приложения открытые свойства или методы, которые будет использовать код скрипта.</span><span class="sxs-lookup"><span data-stu-id="84370-116">Implement public properties or methods in your application code that your script code will use.</span></span>  
  
     <span data-ttu-id="84370-117">Например, если для объекта скрипта используется класс формы, добавьте в этот класс приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="84370-117">For example, if you use the form class for the scripting object, add the following code to your form class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#5)]  
  
6.  <span data-ttu-id="84370-118">Используйте объект `window.external` в коде скрипта для доступа к открытым свойствам и методам указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="84370-118">Use the `window.external` object in your scripting code to access public properties and methods of the specified object.</span></span>  
  
     <span data-ttu-id="84370-119">Во фрагменте кода HTML ниже показано, как вызвать метод объекта скрипта после нажатия на кнопку.</span><span class="sxs-lookup"><span data-stu-id="84370-119">The following HTML code demonstrates how to call a method on the scripting object from a button click.</span></span> <span data-ttu-id="84370-120">Скопируйте этот код в элемент BODY документа HTML, загруженного с помощью метода <xref:System.Windows.Forms.WebBrowser.Navigate%2A> элемента управления или назначенного свойству <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>.</span><span class="sxs-lookup"><span data-stu-id="84370-120">Copy this code into the BODY element of an HTML document that you load using the control's <xref:System.Windows.Forms.WebBrowser.Navigate%2A> method or that you assign to the control's <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property.</span></span>  
  
    ```  
    <button onclick="window.external.Test('called from script code')">  
        call client code from script code  
    </button>  
    ```  
  
7.  <span data-ttu-id="84370-121">Реализуйте в коде скрипта функции, которые будет использовать код приложения.</span><span class="sxs-lookup"><span data-stu-id="84370-121">Implement functions in your script code that your application code will use.</span></span>  
  
     <span data-ttu-id="84370-122">Пример такой функции представлен в HTML-элементе SCRIPT ниже.</span><span class="sxs-lookup"><span data-stu-id="84370-122">The following HTML SCRIPT element provides an example function.</span></span> <span data-ttu-id="84370-123">Скопируйте этот код в элемент HEAD документа HTML, загруженного с помощью метода <xref:System.Windows.Forms.WebBrowser.Navigate%2A> элемента управления или назначенного свойству <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>.</span><span class="sxs-lookup"><span data-stu-id="84370-123">Copy this code into the HEAD element of an HTML document that you load using the control's <xref:System.Windows.Forms.WebBrowser.Navigate%2A> method or that you assign to the control's <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property.</span></span>  
  
    ```  
    <script>  
    function test(message) {   
        alert(message);   
    }  
    </script>  
    ```  
  
8.  <span data-ttu-id="84370-124">Используйте свойство <xref:System.Windows.Forms.WebBrowser.Document%2A> для доступа к коду скрипта из кода клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="84370-124">Use the <xref:System.Windows.Forms.WebBrowser.Document%2A> property to access the script code from your client application code.</span></span>  
  
     <span data-ttu-id="84370-125">Например, добавьте приведенный ниже код в обработчик событий кнопки <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="84370-125">For example, add the following code to a button <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#8)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#8)]  
  
9. <span data-ttu-id="84370-126">По окончании отладки кода DHTML присвойте свойству <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> значение `true`, чтобы элемент управления <xref:System.Windows.Forms.WebBrowser> не выводил сообщения об ошибках в коде скрипта.</span><span class="sxs-lookup"><span data-stu-id="84370-126">When you are finished debugging your DHTML, set the control's <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> property to `true` to prevent the <xref:System.Windows.Forms.WebBrowser> control from displaying error messages for script code problems.</span></span>  
  
     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#9)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="84370-127">Пример</span><span class="sxs-lookup"><span data-stu-id="84370-127">Example</span></span>  
 <span data-ttu-id="84370-128">В примере ниже приводится полный код демонстрационного приложения, которое поможет лучше разобраться в описываемой возможности.</span><span class="sxs-lookup"><span data-stu-id="84370-128">The following complete code example provides a demonstration application that you can use to understand this feature.</span></span> <span data-ttu-id="84370-129">Код HTML загружается в элемент управления <xref:System.Windows.Forms.WebBrowser> посредством свойства <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> вместо загрузки из отдельного HTML-файла.</span><span class="sxs-lookup"><span data-stu-id="84370-129">The HTML code is loaded into the <xref:System.Windows.Forms.WebBrowser> control through the <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property instead of being loaded from a separate HTML file.</span></span>  
  
 [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="84370-130">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="84370-130">Compiling the Code</span></span>  
 <span data-ttu-id="84370-131">Для этого примера кода требуются:</span><span class="sxs-lookup"><span data-stu-id="84370-131">This code requires:</span></span>  
  
-   <span data-ttu-id="84370-132">ссылки на сборки System и System.Windows.Forms;</span><span class="sxs-lookup"><span data-stu-id="84370-132">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="84370-133">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="84370-133">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="84370-134">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="84370-134">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84370-135">См. также</span><span class="sxs-lookup"><span data-stu-id="84370-135">See also</span></span>
- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.Document%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A?displayProperty=nameWithType>
- [<span data-ttu-id="84370-136">Элемент управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="84370-136">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
