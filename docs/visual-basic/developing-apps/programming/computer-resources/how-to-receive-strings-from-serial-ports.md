---
title: "Практическое руководство. Получение строк из последовательных портов в Visual Basic"
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
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
caps.latest.revision: 21
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
ms.openlocfilehash: 500a6c651f6eb991eb9fefef601d0f593a38352f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a><span data-ttu-id="4d35f-102">Практическое руководство. Получение строк из последовательных портов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d35f-102">How to: Receive Strings From Serial Ports in Visual Basic</span></span>
<span data-ttu-id="4d35f-103">В этом разделе описывается, как использовать `My.Computer.Ports` для получения строк из последовательных портов компьютера в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d35f-103">This topic describes how to use `My.Computer.Ports` to receive strings from the computer's serial ports in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
### <a name="to-receive-strings-from-the-serial-port"></a><span data-ttu-id="4d35f-104">Получение строк из последовательного порта</span><span class="sxs-lookup"><span data-stu-id="4d35f-104">To receive strings from the serial port</span></span>  
  
1.  <span data-ttu-id="4d35f-105">Инициализируйте возвращаемую строку.</span><span class="sxs-lookup"><span data-stu-id="4d35f-105">Initialize the return string.</span></span>  
  
     <span data-ttu-id="4d35f-106">[!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4d35f-106">[!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]</span></span>  
  
2.  <span data-ttu-id="4d35f-107">Определите, какой последовательный порт должен предоставлять строки.</span><span class="sxs-lookup"><span data-stu-id="4d35f-107">Determine which serial port should provide the strings.</span></span> <span data-ttu-id="4d35f-108">В этом примере предполагается, что это `COM1`.</span><span class="sxs-lookup"><span data-stu-id="4d35f-108">This example assumes it is `COM1`.</span></span>  
  
3.  <span data-ttu-id="4d35f-109">Воспользуйтесь методом `My.Computer.Ports.OpenSerialPort`, чтобы получить ссылку на порт.</span><span class="sxs-lookup"><span data-stu-id="4d35f-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="4d35f-110">Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d35f-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="4d35f-111">Блок `Try...Catch...Finally` позволяет приложению закрыть последовательный порт даже в том случае, если он создает исключение.</span><span class="sxs-lookup"><span data-stu-id="4d35f-111">The `Try...Catch...Finally` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="4d35f-112">В этом блоке должен отображаться весь код, управляющий последовательным портом.</span><span class="sxs-lookup"><span data-stu-id="4d35f-112">All code that manipulates the serial port should appear within this block.</span></span>  
  
     <span data-ttu-id="4d35f-113">[!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4d35f-113">[!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]</span></span>  
  
4.  <span data-ttu-id="4d35f-114">Создайте цикл `Do`, который будет читать строки текста до тех пор, пока они не закончатся.</span><span class="sxs-lookup"><span data-stu-id="4d35f-114">Create a `Do` loop for reading lines of text until no more lines are available.</span></span>  
  
     <span data-ttu-id="4d35f-115">[!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="4d35f-115">[!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]</span></span>  
  
5.  <span data-ttu-id="4d35f-116">Используйте метод <xref:System.IO.Ports.SerialPort.ReadLine%2A> для чтения следующей доступной строки текста из последовательного порта.</span><span class="sxs-lookup"><span data-stu-id="4d35f-116">Use the <xref:System.IO.Ports.SerialPort.ReadLine%2A> method to read the next available line of text from the serial port.</span></span>  
  
     <span data-ttu-id="4d35f-117">[!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="4d35f-117">[!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]</span></span>  
  
6.  <span data-ttu-id="4d35f-118">С помощью оператора `If` проверьте, возвращает ли метод <xref:System.IO.Ports.SerialPort.ReadLine%2A> значение `Nothing` (которое означает, что больше нет доступного текста).</span><span class="sxs-lookup"><span data-stu-id="4d35f-118">Use an `If` statement to determine if the <xref:System.IO.Ports.SerialPort.ReadLine%2A> method returns `Nothing` (which means no more text is available).</span></span> <span data-ttu-id="4d35f-119">Если он возвращает `Nothing`, завершите цикл `Do`.</span><span class="sxs-lookup"><span data-stu-id="4d35f-119">If it does return `Nothing`, exit the `Do` loop.</span></span>  
  
     <span data-ttu-id="4d35f-120">[!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="4d35f-120">[!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]</span></span>  
  
7.  <span data-ttu-id="4d35f-121">Добавьте в оператор `If` блок `Else` — он будет использоваться, если строка уже прочитана.</span><span class="sxs-lookup"><span data-stu-id="4d35f-121">Add an `Else` block to the `If` statement to handle the case if the string is actually read.</span></span> <span data-ttu-id="4d35f-122">Этот блок прикрепляет строку из последовательного порта к возвращаемой строке.</span><span class="sxs-lookup"><span data-stu-id="4d35f-122">The block appends the string from the serial port to the return string.</span></span>  
  
     <span data-ttu-id="4d35f-123">[!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="4d35f-123">[!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]</span></span>  
  
8.  <span data-ttu-id="4d35f-124">Возвратите строку.</span><span class="sxs-lookup"><span data-stu-id="4d35f-124">Return the string.</span></span>  
  
     <span data-ttu-id="4d35f-125">[!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="4d35f-125">[!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d35f-126">Пример</span><span class="sxs-lookup"><span data-stu-id="4d35f-126">Example</span></span>  
 <span data-ttu-id="4d35f-127">[!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="4d35f-127">[!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]</span></span>  
  
 <span data-ttu-id="4d35f-128">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4d35f-128">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="4d35f-129">В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**.</span><span class="sxs-lookup"><span data-stu-id="4d35f-129">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="4d35f-130">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="4d35f-130">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4d35f-131">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="4d35f-131">Compiling the Code</span></span>  
 <span data-ttu-id="4d35f-132">В этом примере предполагается, что компьютер использует `COM1`.</span><span class="sxs-lookup"><span data-stu-id="4d35f-132">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4d35f-133">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="4d35f-133">Robust Programming</span></span>  
 <span data-ttu-id="4d35f-134">В этом примере предполагается, что компьютер использует `COM1`.</span><span class="sxs-lookup"><span data-stu-id="4d35f-134">This example assumes the computer is using `COM1`.</span></span> <span data-ttu-id="4d35f-135">Для большей гибкости код должен позволять пользователю выбирать нужный последовательный порт из списка доступных портов.</span><span class="sxs-lookup"><span data-stu-id="4d35f-135">For more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="4d35f-136">Дополнительные сведения см. в разделе [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="4d35f-136">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="4d35f-137">В этом примере блок `Try...Catch...Finally` позволяет сделать так, чтобы приложение закрыло порт и перехватило все исключения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="4d35f-137">This example uses a `Try...Catch...Finally` block to make sure that the application closes the port and to catch any timeout exceptions.</span></span> <span data-ttu-id="4d35f-138">Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4d35f-138">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d35f-139">См. также</span><span class="sxs-lookup"><span data-stu-id="4d35f-139">See Also</span></span>  
 <span data-ttu-id="4d35f-140"><xref:Microsoft.VisualBasic.Devices.Ports></span><span class="sxs-lookup"><span data-stu-id="4d35f-140"><xref:Microsoft.VisualBasic.Devices.Ports></span></span>   
 <span data-ttu-id="4d35f-141"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4d35f-141"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span></span>   
 <span data-ttu-id="4d35f-142">[Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="4d35f-142">[How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span></span>  
 <span data-ttu-id="4d35f-143">[Практическое руководство. Отправка строк в последовательные порты](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="4d35f-143">[How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span></span>  
 [<span data-ttu-id="4d35f-144">Практическое руководство. Отображение доступных последовательных портов</span><span class="sxs-lookup"><span data-stu-id="4d35f-144">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)

