---
title: "Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера, в Visual Basic | Microsoft Docs"
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
  - "модемы, выполнение звонков"
  - "My.Computer.Ports - объект"
  - "последовательные порты, выполнение звонков"
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера, в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В этом разделе описывается использование объекта `My.Computer.Ports` для дозвона при помощи модема в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 Как правило, модем подключается к одному из последовательных портов компьютера.  Для взаимодействия с модемом приложение должно отправлять команды на соответствующий последовательный порт.  
  
### Дозвон с помощью модема  
  
1.  Выясните, к какому последовательному порту подключен модем.  В этом примере предполагается, что модем подключен к порту COM1.  
  
2.  Используйте метод `My.Computer.Ports.OpenSerialPort` для получения ссылки на порт.  Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     Блок `Using` позволяет приложению закрыть последовательный порт даже в случае возникновения исключения.  Весь код, управляющий последовательным портом, должен содержаться внутри этого блока или внутри блока `Try...Catch...Finally`.  
  
     [!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#28)]  
  
3.  Задайте свойство `DtrEnable`, чтобы указать, что компьютер готов принять входящие данные от модема.  
  
     [!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#29)]  
  
4.  Отправьте модему через последовательный порт команду дозвона и телефонный номер с помощью метода <xref:System.IO.Ports.SerialPort.Write%2A>.  
  
     [!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#30)]  
  
## Пример  
 [!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#27)]  
  
 Данный пример кода доступен также в качестве фрагмента кода IntelliSense.  В окне выбора фрагмента кода он находится в разделе **Связь и сеть**.  Дополнительные сведения см. в разделе [Фрагменты кода](/visual-studio/ide/code-snippets).  
  
## Компиляция кода  
 В этом примере требуется ссылка на пространство имен <xref:System?displayProperty=fullName>.  
  
## Отказоустойчивость  
 В этом примере предполагается, что модем подключен к порту COM1.  Рекомендуется предоставить пользователю возможность выбора нужного последовательного порта в списке доступных портов.  Дополнительные сведения см. в разделе [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 В этом примере используется блок `Using`, чтобы обеспечить закрытие порта приложением даже в случае возникновения исключения.  Дополнительные сведения см. в разделе [Оператор Using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
 В этом примере приложение отключает последовательный порт после осуществления дозвона до модема.  В реальной ситуации может потребоваться передавать данные в модем и получать их от модема.  Дополнительные сведения см. в разделе [Практическое руководство. Получение строк из последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).  
  
## См. также  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [Практическое руководство. Отправка строк в последовательный порт](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [Практическое руководство. Получение строк из последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)   
 [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)