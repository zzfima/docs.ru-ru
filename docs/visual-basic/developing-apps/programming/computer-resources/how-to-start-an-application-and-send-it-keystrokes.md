---
title: "Практическое руководство. Запуск приложения и отправка ему нажатий клавиш (Visual Basic) | Microsoft Docs"
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
  - "нажатия клавиш, отправка"
  - "процессы, запуск и отправка сведений о нажатии клавиш"
  - "SendKeys.SendWait - примеры"
  - "Shell - пример команды [Visual Basic]"
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Практическое руководство. Запуск приложения и отправка ему нажатий клавиш (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В этом примере используется функция `Shell` для запуска приложения "Калькулятор", а затем перемножается 2 числа путем отправки событий нажатия клавиш с помощью метода `My.Computer.Keyboard.SendKeys`.  
  
## Пример  
 [!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]  
  
## Отказоустойчивость  
 Если приложение с запрошенным идентификатором процесса не найдено, возникает исключение <xref:System.ArgumentException>.  
  
## Безопасность платформы .NET Framework  
 Вызов функции `Shell` требует полного доверия \(класс <xref:System.Security.SecurityException>\).  
  
## См. также  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>   
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>