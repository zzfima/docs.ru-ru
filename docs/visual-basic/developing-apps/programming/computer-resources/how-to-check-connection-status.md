---
title: "Практическое руководство. Проверка состояния подключения в Visual Basic"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3654eb51bb47317c2dc7bf74979a847438b0ae8
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-check-connection-status-in-visual-basic"></a>Практическое руководство. Проверка состояния подключения в Visual Basic
Свойство <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A> можно использовать, чтобы проверить наличие на компьютере подключения к действующей сети или Интернету.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a>Проверка наличия на компьютере рабочего подключения  
  
-   Определите, имеет ли свойство `IsAvailable` значение `True` или `False`. Следующий код проверяет состояние свойства и сообщает его:  
  
     [!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]  
  
     Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**. Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>

