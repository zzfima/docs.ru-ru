---
title: Практическое руководство. Проверка состояния подключения в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: 1a03b181c2e363c3380c4f9858b629713641f2c2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620671"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a>Практическое руководство. Проверка состояния подключения в Visual Basic
Свойство <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> можно использовать, чтобы проверить наличие на компьютере подключения к действующей сети или Интернету.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a>Проверка наличия на компьютере рабочего подключения  
  
- Определите, имеет ли свойство `IsAvailable` значение `True` или `False`. Следующий код проверяет состояние свойства и сообщает его:  
  
     [!code-vb[VbResourceTasks#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#3)]  
  
     Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**. Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>
