---
title: Практическое руководство. Получение строк из последовательных портов
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
ms.openlocfilehash: afd19877d053cb414f08761cda4e461d88f9e21c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345599"
---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a><span data-ttu-id="96391-102">Практическое руководство. Получение строк из последовательных портов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96391-102">How to: Receive Strings From Serial Ports in Visual Basic</span></span>

<span data-ttu-id="96391-103">В этом разделе описывается, как использовать `My.Computer.Ports` для получения строк из последовательных портов компьютера в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="96391-103">This topic describes how to use `My.Computer.Ports` to receive strings from the computer's serial ports in Visual Basic.</span></span>  
  
### <a name="to-receive-strings-from-the-serial-port"></a><span data-ttu-id="96391-104">Получение строк из последовательного порта</span><span class="sxs-lookup"><span data-stu-id="96391-104">To receive strings from the serial port</span></span>  
  
1. <span data-ttu-id="96391-105">Инициализируйте возвращаемую строку.</span><span class="sxs-lookup"><span data-stu-id="96391-105">Initialize the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#38)]  
  
2. <span data-ttu-id="96391-106">Определите, какой последовательный порт должен предоставлять строки.</span><span class="sxs-lookup"><span data-stu-id="96391-106">Determine which serial port should provide the strings.</span></span> <span data-ttu-id="96391-107">В этом примере предполагается, что это `COM1`.</span><span class="sxs-lookup"><span data-stu-id="96391-107">This example assumes it is `COM1`.</span></span>  
  
3. <span data-ttu-id="96391-108">Воспользуйтесь методом `My.Computer.Ports.OpenSerialPort`, чтобы получить ссылку на порт.</span><span class="sxs-lookup"><span data-stu-id="96391-108">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="96391-109">Дополнительные сведения можно найти по адресу: <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="96391-109">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="96391-110">Блок `Try...Catch...Finally` позволяет приложению закрыть последовательный порт даже в том случае, если он создает исключение.</span><span class="sxs-lookup"><span data-stu-id="96391-110">The `Try...Catch...Finally` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="96391-111">В этом блоке должен отображаться весь код, управляющий последовательным портом.</span><span class="sxs-lookup"><span data-stu-id="96391-111">All code that manipulates the serial port should appear within this block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#39)]  
  
4. <span data-ttu-id="96391-112">Создайте цикл `Do`, который будет читать строки текста до тех пор, пока они не закончатся.</span><span class="sxs-lookup"><span data-stu-id="96391-112">Create a `Do` loop for reading lines of text until no more lines are available.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#40)]  
  
5. <span data-ttu-id="96391-113">Используйте метод <xref:System.IO.Ports.SerialPort.ReadLine> для чтения следующей доступной строки текста из последовательного порта.</span><span class="sxs-lookup"><span data-stu-id="96391-113">Use the <xref:System.IO.Ports.SerialPort.ReadLine> method to read the next available line of text from the serial port.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#41)]  
  
6. <span data-ttu-id="96391-114">С помощью оператора `If` проверьте, возвращает ли метод <xref:System.IO.Ports.SerialPort.ReadLine> значение `Nothing` (которое означает, что больше нет доступного текста).</span><span class="sxs-lookup"><span data-stu-id="96391-114">Use an `If` statement to determine if the <xref:System.IO.Ports.SerialPort.ReadLine> method returns `Nothing` (which means no more text is available).</span></span> <span data-ttu-id="96391-115">Если он возвращает `Nothing`, завершите цикл `Do`.</span><span class="sxs-lookup"><span data-stu-id="96391-115">If it does return `Nothing`, exit the `Do` loop.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#42)]  
  
7. <span data-ttu-id="96391-116">Добавьте в оператор `If` блок `Else` — он будет использоваться, если строка уже прочитана.</span><span class="sxs-lookup"><span data-stu-id="96391-116">Add an `Else` block to the `If` statement to handle the case if the string is actually read.</span></span> <span data-ttu-id="96391-117">Этот блок прикрепляет строку из последовательного порта к возвращаемой строке.</span><span class="sxs-lookup"><span data-stu-id="96391-117">The block appends the string from the serial port to the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#43)]  
  
8. <span data-ttu-id="96391-118">Возвратите строку.</span><span class="sxs-lookup"><span data-stu-id="96391-118">Return the string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#44)]  
  
## <a name="example"></a><span data-ttu-id="96391-119">Пример</span><span class="sxs-lookup"><span data-stu-id="96391-119">Example</span></span>  

 [!code-vb[VbVbalrMyComputer#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#37)]  
  
 <span data-ttu-id="96391-120">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="96391-120">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="96391-121">В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**.</span><span class="sxs-lookup"><span data-stu-id="96391-121">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="96391-122">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="96391-122">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="96391-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="96391-123">Compiling the Code</span></span>  

 <span data-ttu-id="96391-124">В этом примере предполагается, что компьютер использует `COM1`.</span><span class="sxs-lookup"><span data-stu-id="96391-124">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="96391-125">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="96391-125">Robust Programming</span></span>  

 <span data-ttu-id="96391-126">В этом примере предполагается, что компьютер использует `COM1`.</span><span class="sxs-lookup"><span data-stu-id="96391-126">This example assumes the computer is using `COM1`.</span></span> <span data-ttu-id="96391-127">Для большей гибкости код должен позволять пользователю выбирать нужный последовательный порт из списка доступных портов.</span><span class="sxs-lookup"><span data-stu-id="96391-127">For more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="96391-128">Дополнительные сведения см. в разделе [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="96391-128">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="96391-129">В этом примере блок `Try...Catch...Finally` позволяет сделать так, чтобы приложение закрыло порт и перехватило все исключения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="96391-129">This example uses a `Try...Catch...Finally` block to make sure that the application closes the port and to catch any timeout exceptions.</span></span> <span data-ttu-id="96391-130">Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="96391-130">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96391-131">См. также</span><span class="sxs-lookup"><span data-stu-id="96391-131">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="96391-132">Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера</span><span class="sxs-lookup"><span data-stu-id="96391-132">How to: Dial Modems Attached to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [<span data-ttu-id="96391-133">Практическое руководство. Отправка строк в последовательные порты</span><span class="sxs-lookup"><span data-stu-id="96391-133">How to: Send Strings to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [<span data-ttu-id="96391-134">Практическое руководство. Отображение доступных последовательных портов</span><span class="sxs-lookup"><span data-stu-id="96391-134">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
