---
title: Практическое руководство. Запуск приложения и отправка ему нажатий клавиш (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 716c88153ad01c7b225f31948c8aaaa2694dc512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582152"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a>Практическое руководство. Запуск приложения и отправка ему нажатий клавиш (Visual Basic)
В этом примере используется функция `Shell` для запуска приложения "Калькулятор", а затем перемножается два числа путем отправки событий нажатия клавиш с помощью метода `My.Computer.Keyboard.SendKeys`.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если приложение с запрошенным идентификатором процесса не найдено, возникает исключение <xref:System.ArgumentException>.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Вызов функции `Shell` требует полного доверия (класс <xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
