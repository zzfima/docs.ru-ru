---
title: "Практическое руководство. Отображение доступных последовательных портов в Visual Basic | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- serial ports, availability
- My.Computer.Ports.SerialPortNames property
- My.Computer.Ports object
- ports, serial port availability
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cc316600acd5f551dad8fbd4b7260c512231da5e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-show-available-serial-ports-in-visual-basic"></a>Практическое руководство. Отображение доступных последовательных портов в Visual Basic
В этом разделе описывается использование класса `My.Computer.Ports` для отображения доступных последовательных портов компьютера в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Чтобы дать пользователю возможность выбрать используемый порт, имена последовательных портов отображаются в элементе управления <xref:System.Windows.Forms.ListBox>.  
  
## <a name="example"></a>Пример  
 В этом примере циклически перебираются все строки, которые возвращает свойство `My.Computer.Ports.SerialPortNames`. Эти строки представляют собой имена доступных последовательных портов на компьютере.  
  
 Как правило, пользователь выбирает, какой последовательный порт приложение должно использовать из списка доступных портов. В этом примере имена последовательных портов хранятся в элементе управления <xref:System.Windows.Forms.ListBox>. Дополнительные сведения см. в разделе [Элемент управления ListBox](http://msdn.microsoft.com/library/b0172473-c5f2-411e-aaa4-c8f17cb5eed4).  
  
 [!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-show-available-serial-ports_1.vb)]  
  
 Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**. Дополнительные сведения см. в статье [Фрагменты кода](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылка проекта на System.Windows.Forms.dll.  
  
-   Доступ к членам пространства имен <xref:System.Windows.Forms>. Добавьте оператор `Imports`, если в коде не используются полные имена членов. Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
-   В форме должен быть элемент управления <xref:System.Windows.Forms.ListBox> с именем `ListBox1`.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Необязательно использовать элемент управления <xref:System.Windows.Forms.ListBox> для отображения имен доступных последовательных портов. Вместо этого можно использовать <xref:System.Windows.Forms.ComboBox> или другой элемент управления. Если приложение не требует реакции от пользователя, можно использовать для отображения информации элемент управления <xref:System.Windows.Forms.TextBox>.  
  
> [!NOTE]
>  Имена портов, возвращаемые свойством `My.Computer.Ports.SerialPortNames`, могут быть неверными при выполнении программы в Windows 98. Во избежание ошибок приложения используйте обработку исключений, например оператор `Try...Catch...Finally` или оператор `Using`, если для открытия портов необходимо использовать их имена.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 [Практическое руководство. Дозвон при помощи модема, подключенного к последовательному порту компьютера](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [Практическое руководство. Отправка строк в последовательные порты](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [Практическое руководство. Получение строк из последовательных портов](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)
