---
title: "Практическое руководство. Отправка строк в последовательный порт в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Computer.Ports - объект"
  - "порты, отправка строк в"
  - "последовательные порты, отправка строк в"
  - "строки [Visual Basic], отправка в последовательные порты"
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Практическое руководство. Отправка строк в последовательный порт в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В этом разделе описывается способ использования объекта `My.Computer.Ports` в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] для отправки строки в последовательный порт компьютера.  
  
## Пример  
 В этом примере выполнятся отправка строки в последовательный порт COM1.  Возможно, потребуется использовать другой последовательный порт на компьютере.  
  
 Используйте метод `My.Computer.Ports.OpenSerialPort` для получения ссылки на порт.  Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
 Блок `Using` позволяет приложению закрыть последовательный порт даже в случае возникновения исключения.  Весь код для управления последовательным портом должен находиться внутри этого блока или внутри блока `Try...Catch...Finally`.  
  
 Метод <xref:System.IO.Ports.SerialPort.WriteLine%2A> позволяет отправить данные в последовательный порт.  
  
 [!code-vb[VbVbalrMyComputer#33](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#33)]  
  
## Компиляция кода  
  
-   В этом примере предполагается, что на компьютере используется порт `COM1`.  
  
## Отказоустойчивость  
 В этом примере предполагается, что на компьютере используется порт `COM1`. В целях обеспечения большей гибкости код должен позволять пользователю выбирать нужный последовательный порт в списке доступных портов.  Дополнительные сведения см. в разделе [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 В этом примере используется блок `Using`, чтобы обеспечить закрытие порта приложением даже в случае возникновения исключения.  Дополнительные сведения см. в разделе [Оператор Using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## См. также  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)