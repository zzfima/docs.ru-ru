---
title: "Практическое руководство. Проверка состояния подключения в Visual Basic | Microsoft Docs"
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
  - "статус соединения"
  - "подключения, проверка статуса"
  - "IsAvailable - свойство, сведения о IsAvailable"
  - "веб-подключения"
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
caps.latest.revision: 26
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 26
---
# Практическое руководство. Проверка состояния подключения в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Свойство <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A> позволяет определить наличие рабочей сети или подключения к Интернету на компьютере.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Проверка наличия рабочего подключения на компьютере  
  
-   Определите значение свойства `IsAvailable`: `True` или `False`.  Следующий код проверяет значение свойства и сообщает его.  
  
     [!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]  
  
     Данный пример кода доступен также в качестве фрагмента кода IntelliSense.  В окне выбора фрагмента кода он находится в разделе **Связь и сеть**.  Дополнительные сведения см. в разделе [Фрагменты кода](/visual-studio/ide/code-snippets).  
  
## См. также  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>