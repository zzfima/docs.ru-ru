---
title: "Практическое руководство. Отображение доступных последовательных портов в Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- serial ports, availability
- My.Computer.Ports.SerialPortNames property
- My.Computer.Ports object
- ports, serial port availability
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bab6177c788a847b46586db19a525c1a1b36476d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-show-available-serial-ports-in-visual-basic"></a><span data-ttu-id="a0955-102">Практическое руководство. Отображение доступных последовательных портов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0955-102">How to: Show Available Serial Ports in Visual Basic</span></span>
<span data-ttu-id="a0955-103">В этом разделе описывается использование класса `My.Computer.Ports` для отображения доступных последовательных портов компьютера в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0955-103">This topic describes how to use `My.Computer.Ports` to show the available serial ports of the computer in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="a0955-104">Чтобы дать пользователю возможность выбрать используемый порт, имена последовательных портов отображаются в элементе управления <xref:System.Windows.Forms.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="a0955-104">To allow a user to select which port to use, the names of the serial ports are placed in a <xref:System.Windows.Forms.ListBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0955-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a0955-105">Example</span></span>  
 <span data-ttu-id="a0955-106">В этом примере циклически перебираются все строки, которые возвращает свойство `My.Computer.Ports.SerialPortNames`.</span><span class="sxs-lookup"><span data-stu-id="a0955-106">This example loops over all the strings that the `My.Computer.Ports.SerialPortNames` property returns.</span></span> <span data-ttu-id="a0955-107">Эти строки представляют собой имена доступных последовательных портов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a0955-107">These strings are the names of the available serial ports on the computer.</span></span>  
  
 <span data-ttu-id="a0955-108">Как правило, пользователь выбирает, какой последовательный порт приложение должно использовать из списка доступных портов.</span><span class="sxs-lookup"><span data-stu-id="a0955-108">Typically, a user selects which serial port the application should use from the list of available ports.</span></span> <span data-ttu-id="a0955-109">В этом примере имена последовательных портов хранятся в элементе управления <xref:System.Windows.Forms.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="a0955-109">In this example, the serial port names are stored in a <xref:System.Windows.Forms.ListBox> control.</span></span> <span data-ttu-id="a0955-110">Дополнительные сведения см. в разделе [Элемент управления ListBox](../../../../framework/winforms/controls/listbox-control-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a0955-110">For more information, see [ListBox Control](../../../../framework/winforms/controls/listbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="a0955-111">[!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-show-available-serial-ports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a0955-111">[!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-show-available-serial-ports_1.vb)]</span></span>  
  
 <span data-ttu-id="a0955-112">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="a0955-112">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="a0955-113">В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**.</span><span class="sxs-lookup"><span data-stu-id="a0955-113">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="a0955-114">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="a0955-114">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a0955-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a0955-115">Compiling the Code</span></span>  
 <span data-ttu-id="a0955-116">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="a0955-116">This example requires:</span></span>  
  
-   <span data-ttu-id="a0955-117">Ссылка проекта на System.Windows.Forms.dll.</span><span class="sxs-lookup"><span data-stu-id="a0955-117">A project reference to System.Windows.Forms.dll.</span></span>  
  
-   <span data-ttu-id="a0955-118">Доступ к членам пространства имен <xref:System.Windows.Forms>.</span><span class="sxs-lookup"><span data-stu-id="a0955-118">Access to the members of the <xref:System.Windows.Forms> namespace.</span></span> <span data-ttu-id="a0955-119">Добавьте оператор `Imports`, если в коде не используются полные имена членов.</span><span class="sxs-lookup"><span data-stu-id="a0955-119">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="a0955-120">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="a0955-120">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
-   <span data-ttu-id="a0955-121">Ваша форма должна включать элемент управления <xref:System.Windows.Forms.ListBox> с именем `ListBox1`.</span><span class="sxs-lookup"><span data-stu-id="a0955-121">That your form have a <xref:System.Windows.Forms.ListBox> control named `ListBox1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a0955-122">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="a0955-122">Robust Programming</span></span>  
 <span data-ttu-id="a0955-123">Необязательно использовать элемент управления <xref:System.Windows.Forms.ListBox> для отображения имен доступных последовательных портов.</span><span class="sxs-lookup"><span data-stu-id="a0955-123">You do not have to use the <xref:System.Windows.Forms.ListBox> control to display the available serial port names.</span></span> <span data-ttu-id="a0955-124">Вместо него можно использовать <xref:System.Windows.Forms.ComboBox> или другой элемент управления.</span><span class="sxs-lookup"><span data-stu-id="a0955-124">Instead, you can use a <xref:System.Windows.Forms.ComboBox> or other control.</span></span> <span data-ttu-id="a0955-125">Если приложение не требует реакции от пользователя, можно использовать для отображения информации элемент управления <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="a0955-125">If the application does not need a response from the user, you can use a <xref:System.Windows.Forms.TextBox> control to display the information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0955-126">Имена портов, возвращаемые свойством `My.Computer.Ports.SerialPortNames`, могут быть неверными при выполнении программы в Windows 98.</span><span class="sxs-lookup"><span data-stu-id="a0955-126">The port names returned by `My.Computer.Ports.SerialPortNames` may be incorrect when run on Windows 98.</span></span> <span data-ttu-id="a0955-127">Во избежание ошибок приложения используйте обработку исключений, например оператор `Try...Catch...Finally` или оператор `Using`, если для открытия портов необходимо использовать их имена.</span><span class="sxs-lookup"><span data-stu-id="a0955-127">To prevent application errors, use exception handling, such as the `Try...Catch...Finally` statement or the `Using` statement, when using the port names to open ports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0955-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a0955-128">See Also</span></span>  
 <span data-ttu-id="a0955-129"><xref:Microsoft.VisualBasic.Devices.Ports></span><span class="sxs-lookup"><span data-stu-id="a0955-129"><xref:Microsoft.VisualBasic.Devices.Ports></span></span>   
 <span data-ttu-id="a0955-130">[Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="a0955-130">[How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span></span>  
 <span data-ttu-id="a0955-131">[Практическое руководство. Отправка строк в последовательные порты](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="a0955-131">[How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span></span>  
 [<span data-ttu-id="a0955-132">Практическое руководство. Получение строк из последовательных портов</span><span class="sxs-lookup"><span data-stu-id="a0955-132">How to: Receive Strings From Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)

