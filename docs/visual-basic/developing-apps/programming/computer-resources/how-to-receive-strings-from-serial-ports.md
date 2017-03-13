---
title: "Практическое руководство. Получение строк из последовательных портов в Visual Basic | Microsoft Docs"
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
  - "My.Resources - объект"
  - "последовательные порты, извлечение строк"
  - "строки [Visual Basic], извлечение из последовательных портов"
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Практическое руководство. Получение строк из последовательных портов в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В этом разделе описывается, как использовать объект `My.Computer.Ports` в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] для получения строк из последовательных портов компьютера.  
  
### Получение строк из последовательного порта  
  
1.  Инициализируйте возвращаемую строку.  
  
     [!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]  
  
2.  Определите, из какого последовательного порта должны поступать строки.  В данном примере это `COM1`.  
  
3.  Используйте метод `My.Computer.Ports.OpenSerialPort` для получения ссылки на порт.  Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     Блок `Try...Catch...Finally` позволяет приложению закрыть последовательный порт даже в случае возникновения исключения.  Весь код, управляющий последовательным портом, должен содержаться внутри этого блока.  
  
     [!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]  
  
4.  Создайте цикл `Do` для чтения строк текста до тех пор, пока строки не исчерпаются.  
  
     [!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]  
  
5.  Используйте метод <xref:System.IO.Ports.SerialPort.ReadLine%2A> для чтения следующей доступной строки текста из последовательного порта.  
  
     [!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]  
  
6.  Используйте оператор `If`, чтобы определить, не возвратил ли метод <xref:System.IO.Ports.SerialPort.ReadLine%2A> значение `Nothing` \(это означает, что текст более не доступен\).  Если он возвратит `Nothing`, завершите цикл `Do`.  
  
     [!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]  
  
7.  Добавьте блок `Else` в оператор `If`, чтобы обрабатывать случаи, когда строка является фактически прочитанной.  Блок добавляет строку из последовательного порта к возвращаемой строке.  
  
     [!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]  
  
8.  Возвратите строку.  
  
     [!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]  
  
## Пример  
 [!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]  
  
 Данный пример кода доступен также в качестве фрагмента кода IntelliSense.  В окне выбора фрагмента кода он находится в разделе **Связь и сеть**.  Дополнительные сведения см. в разделе [Фрагменты кода](/visual-studio/ide/code-snippets).  
  
## Компиляция кода  
 В этом примере предполагается, что на компьютере используется порт `COM1`.  
  
## Отказоустойчивость  
 В этом примере предполагается, что на компьютере используется порт `COM1`.  Для большей гибкости код должен позволить пользователю выбрать нужный последовательный порт из списка доступных портов.  Дополнительные сведения см. в разделе [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 В этом примере используется блок `Try...Catch...Finally`, чтобы обеспечить закрытие порта приложением и перехватить любые исключения, возникающие во время ожидания.  Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## См. также  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [Практическое руководство. Отправка строк в последовательный порт](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)