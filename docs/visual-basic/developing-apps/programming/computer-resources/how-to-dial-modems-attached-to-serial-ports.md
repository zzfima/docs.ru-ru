---
title: Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера
ms.date: 07/20/2015
helpviewer_keywords:
- modems [Visual Basic], dialing
- serial ports [Visual Basic], dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
ms.openlocfilehash: febec0a8579d34f8ff59066da5b5aa59c1cce6b2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345642"
---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a>Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера, в Visual Basic

В этом разделе описывается использование `My.Computer.Ports` для дозвона с помощью модема в Visual Basic.  
  
 Как правило, модем подключен к одному из последовательных портов на компьютере. Чтобы приложение могло взаимодействовать с модемом, оно должно отправлять команды на соответствующий последовательный порт.  
  
### <a name="to-dial-a-modem"></a>Набор номера модема  
  
1. Определите, к какому последовательному порту подключен модем. В этом примере предполагается, что модем подключен к порту COM1.  
  
2. Воспользуйтесь методом `My.Computer.Ports.OpenSerialPort`, чтобы получить ссылку на порт. Дополнительные сведения можно найти по адресу: <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     Блок `Using` позволяет приложению закрыть последовательный порт даже в том случае, если он создает исключение. В блоке `Try...Catch...Finally` должен отображаться весь код, управляющий последовательным портом.  
  
     [!code-vb[VbVbalrMyComputer#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#28)]  
  
3. Задайте свойство `DtrEnable`, чтобы указать, что компьютер готов принять входящие данные от модема.  
  
     [!code-vb[VbVbalrMyComputer#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#29)]  
  
4. Отправьте команду вызова и номер телефона на модем через последовательный порт с помощью метода <xref:System.IO.Ports.SerialPort.Write%2A>.  
  
     [!code-vb[VbVbalrMyComputer#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#30)]  
  
## <a name="example"></a>Пример  

 [!code-vb[VbVbalrMyComputer#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#27)]  
  
 Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**. Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Компиляция кода  

 В этом примере нужна ссылка на пространство имен <xref:System?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 В этом примере предполагается, что модем подключен к порту COM1. Рекомендуется, чтобы код позволял пользователю выбирать нужный последовательный порт из списка доступных портов. Дополнительные сведения см. в разделе [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 В этом примере блок `Using` позволяет сделать так, чтобы приложение закрыло порт, даже если он создает исключение. Дополнительные сведения см. в разделе [Оператор using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
 В этом примере приложение отключает последовательный порт после вызова модема. В действительности вам потребуется передать данные на модем и получить их от него. Дополнительные сведения см. в разделе [Практическое руководство. Получение строк из последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Практическое руководство. Отправка строк в последовательные порты](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [Практическое руководство. Получение строк из последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)
- [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
