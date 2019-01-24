---
title: Как выполнить Воспроизведение звука, хранящегося в виде ресурса в Windows Forms
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
ms.openlocfilehash: 390f70acc99d8950a23ce514d90c79c3da765f2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631338"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a>Как выполнить Воспроизведение звука, хранящегося в виде ресурса в Windows Forms
Можно использовать <xref:System.Media.SoundPlayer> класс для воспроизведения звука из внедренного ресурса.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
 Импорт <xref:System.Media?displayProperty=nameWithType> пространства имен.  
  
 включение звукового файла в качестве внедренного ресурса в проект;  
  
 замена "\<AssemblyName>" именем сборки, в которую внедрен звуковой файл. Не включайте суффикс .dll.  
  
## <a name="see-also"></a>См. также
- <xref:System.Media.SoundPlayer>
- [Практическое руководство. Воспроизведение звука в Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
- [Практическое руководство. Цикл звуков в Windows Forms](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)
