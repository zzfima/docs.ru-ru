---
title: "Практическое руководство. Воспроизведение звука, хранящегося в виде ресурса, в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 82e143a6c405d4f3065c18a1a118891e0e692b93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a>Практическое руководство. Воспроизведение звука, хранящегося в виде ресурса, в Windows Forms
Можно использовать <xref:System.Media.SoundPlayer> класса для воспроизведения звука из внедренного ресурса.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
 Импорт <xref:System.Media?displayProperty=nameWithType> пространства имен.  
  
 включение звукового файла в качестве внедренного ресурса в проект;  
  
 замена "\<AssemblyName>" именем сборки, в которую внедрен звуковой файл. Не включайте суффикс .dll.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Media.SoundPlayer>  
 [Практическое руководство. Воспроизведение звука в Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 [Практическое руководство. Циклическое воспроизведение звука в Windows Forms](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)
