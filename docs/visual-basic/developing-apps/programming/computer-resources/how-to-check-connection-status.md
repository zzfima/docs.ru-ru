---
title: "Практическое руководство. Проверка состояния подключения в Visual Basic | Документы Майкрософт"
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
- Web connections
- IsAvailable property, about IsAvailable
- connections, checking status
- connection status
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4163a16e7c338c5e55751a9567fc85109867cfda
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-check-connection-status-in-visual-basic"></a>Практическое руководство. Проверка состояния подключения в Visual Basic
Свойство <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A> можно использовать, чтобы проверить наличие на компьютере подключения к действующей сети или Интернету.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a>Проверка наличия на компьютере рабочего подключения  
  
-   Определите, имеет ли свойство `IsAvailable` значение `True` или `False`. Следующий код проверяет состояние свойства и сообщает его:  
  
     [!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]  
  
     Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**. Дополнительные сведения см. в статье [Фрагменты кода](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>

