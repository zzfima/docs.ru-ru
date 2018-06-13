---
title: Практическое руководство. Воспроизведение звука, хранящегося в виде ресурса, в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
ms.openlocfilehash: c9dc8499e2d12ed17f9b409a805148d08da894fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532139"
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
