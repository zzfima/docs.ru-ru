---
title: Практическое руководство. Запуск приложения и отправка ему нажатий клавиш (Visual Basic)
ms.date: 10/23/2019
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 033999c07bb5839a264122b2ca330916bdf844b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "72919395"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a>Практическое руководство. Запуск приложения и отправка ему нажатий клавиш (Visual Basic)

Этот пример использует метод <xref:Microsoft.VisualBasic.Interaction.Shell%2A> для запуска приложения "Блокнот", а затем распечатывает предложение, отправляя нажатия клавиш с помощью метода [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A).

## <a name="example"></a>Пример

[!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]

## <a name="robust-programming"></a>Отказоустойчивость

Если приложение с запрошенным идентификатором процесса не найдено, возникает исключение <xref:System.ArgumentException>.  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework

Вызов функции `Shell` требует полного доверия (класс <xref:System.Security.SecurityException>).

## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
