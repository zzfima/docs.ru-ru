---
title: Как выполнить Дозвон при помощи модема, подключенного к последовательному порту компьютера, в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- modems [Visual Basic], dialing
- serial ports [Visual Basic], dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
ms.openlocfilehash: db99f94d27235a7c9dca4fc5339854a39147b585
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490617"
---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a><span data-ttu-id="0bd5e-102">Как выполнить Дозвон при помощи модема, подключенного к последовательному порту компьютера, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0bd5e-102">How to: Dial Modems Attached to Serial Ports in Visual Basic</span></span>
<span data-ttu-id="0bd5e-103">В этом разделе описывается использование `My.Computer.Ports` для дозвона с помощью модема в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-103">This topic describes how to use `My.Computer.Ports` to dial a modem in Visual Basic.</span></span>  
  
 <span data-ttu-id="0bd5e-104">Как правило, модем подключен к одному из последовательных портов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-104">Typically, the modem is connected to one of the serial ports on the computer.</span></span> <span data-ttu-id="0bd5e-105">Чтобы приложение могло взаимодействовать с модемом, оно должно отправлять команды на соответствующий последовательный порт.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-105">For your application to communicate with the modem, it must send commands to the appropriate serial port.</span></span>  
  
### <a name="to-dial-a-modem"></a><span data-ttu-id="0bd5e-106">Набор номера модема</span><span class="sxs-lookup"><span data-stu-id="0bd5e-106">To dial a modem</span></span>  
  
1.  <span data-ttu-id="0bd5e-107">Определите, к какому последовательному порту подключен модем.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-107">Determine which serial port the modem is connected to.</span></span> <span data-ttu-id="0bd5e-108">В этом примере предполагается, что модем подключен к порту COM1.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-108">This example assumes the modem is on COM1.</span></span>  
  
2.  <span data-ttu-id="0bd5e-109">Воспользуйтесь методом `My.Computer.Ports.OpenSerialPort`, чтобы получить ссылку на порт.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="0bd5e-110">Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="0bd5e-111">Блок `Using` позволяет приложению закрыть последовательный порт даже в том случае, если он создает исключение.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-111">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="0bd5e-112">В блоке `Try...Catch...Finally` должен отображаться весь код, управляющий последовательным портом.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-112">All code that manipulates the serial port should appear within this block, or within a `Try...Catch...Finally` block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_1.vb)]  
  
3.  <span data-ttu-id="0bd5e-113">Задайте свойство `DtrEnable`, чтобы указать, что компьютер готов принять входящие данные от модема.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-113">Set the `DtrEnable` property to indicate that the computer is ready to accept an incoming transmission from the modem.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_2.vb)]  
  
4.  <span data-ttu-id="0bd5e-114">Отправьте команду вызова и номер телефона на модем через последовательный порт с помощью метода <xref:System.IO.Ports.SerialPort.Write%2A>.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-114">Send the dial command and the phone number to the modem through the serial port by means of the <xref:System.IO.Ports.SerialPort.Write%2A> method.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="0bd5e-115">Пример</span><span class="sxs-lookup"><span data-stu-id="0bd5e-115">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_4.vb)]  
  
 <span data-ttu-id="0bd5e-116">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-116">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="0bd5e-117">В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-117">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="0bd5e-118">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="0bd5e-118">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0bd5e-119">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0bd5e-119">Compiling the Code</span></span>  
 <span data-ttu-id="0bd5e-120">В этом примере нужна ссылка на пространство имен <xref:System?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-120">This example requires a reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0bd5e-121">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="0bd5e-121">Robust Programming</span></span>  
 <span data-ttu-id="0bd5e-122">В этом примере предполагается, что модем подключен к порту COM1.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-122">This example assumes the modem is connected to COM1.</span></span> <span data-ttu-id="0bd5e-123">Рекомендуется, чтобы код позволял пользователю выбирать нужный последовательный порт из списка доступных портов.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-123">We recommend that your code allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="0bd5e-124">Дополнительные сведения см. в разделе [Как Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="0bd5e-124">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="0bd5e-125">В этом примере блок `Using` позволяет сделать так, чтобы приложение закрыло порт, даже если он создает исключение.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-125">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="0bd5e-126">Дополнительные сведения см. в разделе [Оператор using](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0bd5e-126">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
 <span data-ttu-id="0bd5e-127">В этом примере приложение отключает последовательный порт после вызова модема.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-127">In this example, the application disconnects the serial port after it dials the modem.</span></span> <span data-ttu-id="0bd5e-128">В действительности вам потребуется передать данные на модем и получить их от него.</span><span class="sxs-lookup"><span data-stu-id="0bd5e-128">Realistically, you will want to transfer data to and from the modem.</span></span> <span data-ttu-id="0bd5e-129">Дополнительные сведения см. в разделе [Как Получение строк из последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="0bd5e-129">For more information, see [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bd5e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="0bd5e-130">See also</span></span>
- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="0bd5e-131">Практическое руководство. Отправка строк в последовательные порты</span><span class="sxs-lookup"><span data-stu-id="0bd5e-131">How to: Send Strings to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [<span data-ttu-id="0bd5e-132">Практическое руководство. Получение строк из последовательных портов</span><span class="sxs-lookup"><span data-stu-id="0bd5e-132">How to: Receive Strings From Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)
- [<span data-ttu-id="0bd5e-133">Практическое руководство. Отображение доступных последовательных портов</span><span class="sxs-lookup"><span data-stu-id="0bd5e-133">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
