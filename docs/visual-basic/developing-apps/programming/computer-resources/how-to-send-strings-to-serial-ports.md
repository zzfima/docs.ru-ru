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
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a>Практическое руководство. Отправка строк в последовательный порт в Visual Basic

В этом разделе описывается, как использовать `My.Computer.Ports` для отправки строк в последовательные порты компьютера в Visual Basic.  
  
## <a name="example"></a>Пример  

 Этот пример кода отправляет строку в последовательный порт COM1. Возможно, на вашем компьютере потребуется использовать другой последовательный порт.  
  
 Воспользуйтесь методом `My.Computer.Ports.OpenSerialPort`, чтобы получить ссылку на порт. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
 Блок `Using` позволяет приложению закрыть последовательный порт даже в том случае, если он создает исключение. В блоке `Try...Catch...Finally` должен отображаться весь код, управляющий последовательным портом.  
  
 Метод <xref:System.IO.Ports.SerialPort.WriteLine%2A> отправляет данные в последовательный порт.  
  
 [!code-vb[VbVbalrMyComputer#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#33)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- В этом примере предполагается, что компьютер использует `COM1`.  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 В этом примере предполагается, что компьютер использует `COM1`. Для большей гибкости код должен позволять пользователю выбирать нужный последовательный порт из списка доступных портов. Дополнительные сведения см. в разделе [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 В этом примере блок `Using` позволяет сделать так, чтобы приложение закрыло порт, даже если он создает исключение. Дополнительные сведения см. в разделе [Оператор using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
