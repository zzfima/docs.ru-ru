---
title: "Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера, в Visual Basic"
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
- modems, dialing
- serial ports, dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
caps.latest.revision: 19
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
ms.openlocfilehash: 0daaf35cdebac3d69ddc536124d4c86b96955b11
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a><span data-ttu-id="5b8c1-102">Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5b8c1-102">How to: Dial Modems Attached to Serial Ports in Visual Basic</span></span>
<span data-ttu-id="5b8c1-103">В этом разделе описывается использование `My.Computer.Ports` для подключения к модему в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b8c1-103">This topic describes how to use `My.Computer.Ports` to dial a modem in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="5b8c1-104">Как правило, модем подключен к одному из последовательных портов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-104">Typically, the modem is connected to one of the serial ports on the computer.</span></span> <span data-ttu-id="5b8c1-105">Чтобы приложение могло взаимодействовать с модемом, оно должно отправлять команды на соответствующий последовательный порт.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-105">For your application to communicate with the modem, it must send commands to the appropriate serial port.</span></span>  
  
### <a name="to-dial-a-modem"></a><span data-ttu-id="5b8c1-106">Набор номера модема</span><span class="sxs-lookup"><span data-stu-id="5b8c1-106">To dial a modem</span></span>  
  
1.  <span data-ttu-id="5b8c1-107">Определите, к какому последовательному порту подключен модем.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-107">Determine which serial port the modem is connected to.</span></span> <span data-ttu-id="5b8c1-108">В этом примере предполагается, что модем подключен к порту COM1.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-108">This example assumes the modem is on COM1.</span></span>  
  
2.  <span data-ttu-id="5b8c1-109">Воспользуйтесь методом `My.Computer.Ports.OpenSerialPort`, чтобы получить ссылку на порт.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="5b8c1-110">Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="5b8c1-111">Блок `Using` позволяет приложению закрыть последовательный порт даже в том случае, если он создает исключение.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-111">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="5b8c1-112">В блоке `Try...Catch...Finally` должен отображаться весь код, управляющий последовательным портом.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-112">All code that manipulates the serial port should appear within this block, or within a `Try...Catch...Finally` block.</span></span>  
  
     <span data-ttu-id="5b8c1-113">[!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5b8c1-113">[!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_1.vb)]</span></span>  
  
3.  <span data-ttu-id="5b8c1-114">Задайте свойство `DtrEnable`, чтобы указать, что компьютер готов принять входящие данные от модема.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-114">Set the `DtrEnable` property to indicate that the computer is ready to accept an incoming transmission from the modem.</span></span>  
  
     <span data-ttu-id="5b8c1-115">[!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5b8c1-115">[!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_2.vb)]</span></span>  
  
4.  <span data-ttu-id="5b8c1-116">Отправьте команду вызова и номер телефона на модем через последовательный порт с помощью метода <xref:System.IO.Ports.SerialPort.Write%2A>.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-116">Send the dial command and the phone number to the modem through the serial port by means of the <xref:System.IO.Ports.SerialPort.Write%2A> method.</span></span>  
  
     <span data-ttu-id="5b8c1-117">[!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="5b8c1-117">[!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b8c1-118">Пример</span><span class="sxs-lookup"><span data-stu-id="5b8c1-118">Example</span></span>  
 <span data-ttu-id="5b8c1-119">[!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="5b8c1-119">[!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_4.vb)]</span></span>  
  
 <span data-ttu-id="5b8c1-120">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-120">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="5b8c1-121">В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-121">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="5b8c1-122">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="5b8c1-122">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5b8c1-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="5b8c1-123">Compiling the Code</span></span>  
 <span data-ttu-id="5b8c1-124">В этом примере нужна ссылка на пространство имен <xref:System?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-124">This example requires a reference to the <xref:System?displayProperty=fullName> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5b8c1-125">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="5b8c1-125">Robust Programming</span></span>  
 <span data-ttu-id="5b8c1-126">В этом примере предполагается, что модем подключен к порту COM1.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-126">This example assumes the modem is connected to COM1.</span></span> <span data-ttu-id="5b8c1-127">Рекомендуется, чтобы код позволял пользователю выбирать нужный последовательный порт из списка доступных портов.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-127">We recommend that your code allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="5b8c1-128">Дополнительные сведения см. в разделе [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="5b8c1-128">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="5b8c1-129">В этом примере блок `Using` позволяет сделать так, чтобы приложение закрыло порт, даже если он создает исключение.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-129">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="5b8c1-130">Дополнительные сведения см. в разделе [Оператор using](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5b8c1-130">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
 <span data-ttu-id="5b8c1-131">В этом примере приложение отключает последовательный порт после вызова модема.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-131">In this example, the application disconnects the serial port after it dials the modem.</span></span> <span data-ttu-id="5b8c1-132">В действительности вам потребуется передать данные на модем и получить их от него.</span><span class="sxs-lookup"><span data-stu-id="5b8c1-132">Realistically, you will want to transfer data to and from the modem.</span></span> <span data-ttu-id="5b8c1-133">Дополнительные сведения см. в разделе [Практическое руководство. Получение строк из последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="5b8c1-133">For more information, see [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b8c1-134">См. также</span><span class="sxs-lookup"><span data-stu-id="5b8c1-134">See Also</span></span>  
 <span data-ttu-id="5b8c1-135"><xref:Microsoft.VisualBasic.Devices.Ports></span><span class="sxs-lookup"><span data-stu-id="5b8c1-135"><xref:Microsoft.VisualBasic.Devices.Ports></span></span>   
 <span data-ttu-id="5b8c1-136"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5b8c1-136"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span></span>   
 <span data-ttu-id="5b8c1-137">[Практическое руководство. Отправка строк в последовательные порты](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="5b8c1-137">[How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span></span>  
 <span data-ttu-id="5b8c1-138">[Практическое руководство. Получение строк из последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="5b8c1-138">[How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md) </span></span>  
 [<span data-ttu-id="5b8c1-139">Практическое руководство. Отображение доступных последовательных портов</span><span class="sxs-lookup"><span data-stu-id="5b8c1-139">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)

