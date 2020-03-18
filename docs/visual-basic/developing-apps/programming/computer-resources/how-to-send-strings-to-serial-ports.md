---
title: Практическое руководство. Отправка строк в последовательный порт
ms.date: 07/20/2015
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
ms.openlocfilehash: b2051451142a7818a3b7d1bc564c5ae36b2579fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345588"
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a><span data-ttu-id="46079-102">Практическое руководство. Отправка строк в последовательный порт в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46079-102">How to: Send Strings to Serial Ports in Visual Basic</span></span>

<span data-ttu-id="46079-103">В этом разделе описывается, как использовать `My.Computer.Ports` для отправки строк в последовательные порты компьютера в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="46079-103">This topic describes how to use `My.Computer.Ports` to send strings to the computer's serial ports in Visual Basic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46079-104">Пример</span><span class="sxs-lookup"><span data-stu-id="46079-104">Example</span></span>  

 <span data-ttu-id="46079-105">Этот пример кода отправляет строку в последовательный порт COM1.</span><span class="sxs-lookup"><span data-stu-id="46079-105">This example sends a string to the COM1 serial port.</span></span> <span data-ttu-id="46079-106">Возможно, на вашем компьютере потребуется использовать другой последовательный порт.</span><span class="sxs-lookup"><span data-stu-id="46079-106">You may need to use a different serial port on your computer.</span></span>  
  
 <span data-ttu-id="46079-107">Воспользуйтесь методом `My.Computer.Ports.OpenSerialPort`, чтобы получить ссылку на порт.</span><span class="sxs-lookup"><span data-stu-id="46079-107">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="46079-108">Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="46079-108">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
 <span data-ttu-id="46079-109">Блок `Using` позволяет приложению закрыть последовательный порт даже в том случае, если он создает исключение.</span><span class="sxs-lookup"><span data-stu-id="46079-109">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="46079-110">В блоке `Try...Catch...Finally` должен отображаться весь код, управляющий последовательным портом.</span><span class="sxs-lookup"><span data-stu-id="46079-110">All code that manipulates the serial port should appear within this block or within a `Try...Catch...Finally` block.</span></span>  
  
 <span data-ttu-id="46079-111">Метод <xref:System.IO.Ports.SerialPort.WriteLine%2A> отправляет данные в последовательный порт.</span><span class="sxs-lookup"><span data-stu-id="46079-111">The <xref:System.IO.Ports.SerialPort.WriteLine%2A> method sends the data to the serial port.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#33)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="46079-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="46079-112">Compiling the Code</span></span>  
  
- <span data-ttu-id="46079-113">В этом примере предполагается, что компьютер использует `COM1`.</span><span class="sxs-lookup"><span data-stu-id="46079-113">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="46079-114">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="46079-114">Robust Programming</span></span>  

 <span data-ttu-id="46079-115">В этом примере предполагается, что компьютер использует `COM1`. Для большей гибкости код должен позволять пользователю выбирать нужный последовательный порт из списка доступных портов.</span><span class="sxs-lookup"><span data-stu-id="46079-115">This example assumes the computer is using `COM1`; for more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="46079-116">Дополнительные сведения см. в разделе [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="46079-116">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="46079-117">В этом примере блок `Using` позволяет сделать так, чтобы приложение закрыло порт, даже если он создает исключение.</span><span class="sxs-lookup"><span data-stu-id="46079-117">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="46079-118">Дополнительные сведения см. в разделе [Оператор using](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="46079-118">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46079-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="46079-119">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="46079-120">Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера</span><span class="sxs-lookup"><span data-stu-id="46079-120">How to: Dial Modems Attached to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [<span data-ttu-id="46079-121">Практическое руководство. Отображение доступных последовательных портов</span><span class="sxs-lookup"><span data-stu-id="46079-121">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
