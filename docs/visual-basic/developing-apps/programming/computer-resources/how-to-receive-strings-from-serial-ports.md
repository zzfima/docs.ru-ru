---
title: Практическое руководство. Получение строк из последовательных портов
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
ms.openlocfilehash: afd19877d053cb414f08761cda4e461d88f9e21c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345599"
---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a>Практическое руководство. Получение строк из последовательных портов в Visual Basic

В этом разделе описывается, как использовать `My.Computer.Ports` для получения строк из последовательных портов компьютера в Visual Basic.  
  
### <a name="to-receive-strings-from-the-serial-port"></a>Получение строк из последовательного порта  
  
1. Инициализируйте возвращаемую строку.  
  
     [!code-vb[VbVbalrMyComputer#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#38)]  
  
2. Определите, какой последовательный порт должен предоставлять строки. В этом примере предполагается, что это `COM1`.  
  
3. Воспользуйтесь методом `My.Computer.Ports.OpenSerialPort`, чтобы получить ссылку на порт. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     Блок `Try...Catch...Finally` позволяет приложению закрыть последовательный порт даже в том случае, если он создает исключение. В этом блоке должен отображаться весь код, управляющий последовательным портом.  
  
     [!code-vb[VbVbalrMyComputer#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#39)]  
  
4. Создайте цикл `Do`, который будет читать строки текста до тех пор, пока они не закончатся.  
  
     [!code-vb[VbVbalrMyComputer#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#40)]  
  
5. Используйте метод <xref:System.IO.Ports.SerialPort.ReadLine> для чтения следующей доступной строки текста из последовательного порта.  
  
     [!code-vb[VbVbalrMyComputer#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#41)]  
  
6. С помощью оператора `If` проверьте, возвращает ли метод <xref:System.IO.Ports.SerialPort.ReadLine> значение `Nothing` (которое означает, что больше нет доступного текста). Если он возвращает `Nothing`, завершите цикл `Do`.  
  
     [!code-vb[VbVbalrMyComputer#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#42)]  
  
7. Добавьте в оператор `Else` блок `If` — он будет использоваться, если строка уже прочитана. Этот блок прикрепляет строку из последовательного порта к возвращаемой строке.  
  
     [!code-vb[VbVbalrMyComputer#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#43)]  
  
8. Возвратите строку.  
  
     [!code-vb[VbVbalrMyComputer#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#44)]  
  
## <a name="example"></a>Пример  

 [!code-vb[VbVbalrMyComputer#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#37)]  
  
 Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**. Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Компиляция кода  

 В этом примере предполагается, что компьютер использует `COM1`.  
  
## <a name="robust-programming"></a>Отказоустойчивость  

 В этом примере предполагается, что компьютер использует `COM1`. Для большей гибкости код должен позволять пользователю выбирать нужный последовательный порт из списка доступных портов. Дополнительные сведения см. в разделе [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 В этом примере блок `Try...Catch...Finally` позволяет сделать так, чтобы приложение закрыло порт и перехватило все исключения времени ожидания. Дополнительные сведения см. в разделе [Оператор Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [Практическое руководство. Отправка строк в последовательные порты](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [Практическое руководство. Отображение доступных последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
