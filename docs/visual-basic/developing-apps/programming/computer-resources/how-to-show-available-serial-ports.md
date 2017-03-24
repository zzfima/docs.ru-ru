---
title: "Практическое руководство. Отображение доступных последовательных портов в Visual Basic | Microsoft Docs"
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
  - "My.Computer.Ports.SerialPortNames - свойство"
  - "порты, доступность последовательного порта"
  - "последовательные порты, доступность"
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Практическое руководство. Отображение доступных последовательных портов в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В этом разделе описывается использование класса `My.Computer.Ports` для отображения доступных последовательных портов компьютера в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 Чтобы дать пользователю возможность выбрать порт для использования, имена последовательных портов отображаются в элементе управления <xref:System.Windows.Forms.ListBox>.  
  
## Пример  
 В этом примере циклически перебираются все строки, которые возвращает свойство `My.Computer.Ports.SerialPortNames`.  Эти строки представляют собой имена доступных последовательных портов на компьютере.  
  
 Как правило, пользователь выбирает, какой последовательный порт приложение должно использовать из списка доступных портов.  В этом примере имена последовательных портов хранятся в элементе управления <xref:System.Windows.Forms.ListBox>.  Дополнительные сведения см. в разделе [Элемент управления ListBox](../Topic/ListBox%20Control%20\(Windows%20Forms\).md).  
  
 [!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-show-available-serial-ports_1.vb)]  
  
 Данный пример кода доступен также в качестве фрагмента кода IntelliSense.  В окне выбора фрагмента кода он находится в разделе **Связь и сеть**.  Дополнительные сведения см. в разделе [Фрагменты кода](/visual-studio/ide/code-snippets).  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылка проекта на System.Windows.Forms.dll  
  
-   Доступ к элементам пространства имен <xref:System.Windows.Forms>.  Добавьте оператор `Imports`, если в коде не используются полностью квалифицированные имена элементов.  Дополнительные сведения см. в разделе [Оператор Imports \(пространство имен .NET и тип\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
-   В форме должен быть элемент управления <xref:System.Windows.Forms.ListBox> с именем `ListBox1`.  
  
## Отказоустойчивость  
 Нет необходимости использовать элемент управления <xref:System.Windows.Forms.ListBox> для отображения имен доступных последовательных портов.  Вместо этого можно использовать <xref:System.Windows.Forms.ComboBox> или другой элемент управления.  Если приложение не требует ответа от пользователя, можно использовать для отображения информации элемент управления <xref:System.Windows.Forms.TextBox>.  
  
> [!NOTE]
>  Имена портов, возвращаемые свойством `My.Computer.Ports.SerialPortNames`, могут быть неверными при выполнении программы в Windows 98.  Во избежание ошибок приложения используйте обработку исключений, например инструкцию `Try...Catch...Finally` или инструкцию `Using`, если имена портов необходимо использовать для открытия портов.  
  
## См. также  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 [Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [Практическое руководство. Отправка строк в последовательный порт](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [Практическое руководство. Получение строк из последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)