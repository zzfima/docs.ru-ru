---
title: Практическое руководство. Отправка строк в последовательный порт в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
ms.openlocfilehash: a00306407cfe880ebc915d74a753109cc9696f6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a>Практическое руководство. Отправка строк в последовательный порт в Visual Basic
В этом разделе описывается, как использовать `My.Computer.Ports` для отправки строк в последовательные порты компьютера в Visual Basic.  
  
## <a name="example"></a>Пример  
 Этот пример кода отправляет строку в последовательный порт COM1. Возможно, на вашем компьютере потребуется использовать другой последовательный порт.  
  
 Воспользуйтесь методом `My.Computer.Ports.OpenSerialPort`, чтобы получить ссылку на порт. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
 Блок `Using` позволяет приложению закрыть последовательный порт даже в том случае, если он создает исключение. В блоке `Try...Catch...Finally` должен отображаться весь код, управляющий последовательным портом.  
  
 Метод <xref:System.IO.Ports.SerialPort.WriteLine%2A> отправляет данные в последовательный порт.  
  
 [!code-vb[VbVbalrMyComputer#33](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-send-strings-to-serial-ports_1.vb)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   В этом примере предполагается, что компьютер использует `COM1`.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 В этом примере предполагается, что компьютер использует `COM1`. Для большей гибкости код должен позволять пользователю выбирать нужный последовательный порт из списка доступных портов. Дополнительные сведения см. в разделе [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 В этом примере блок `Using` позволяет сделать так, чтобы приложение закрыло порт, даже если он создает исключение. Дополнительные сведения см. в разделе [Оператор using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>  
 [Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)  
 [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
