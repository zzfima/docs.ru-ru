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
ms.openlocfilehash: 49235f9cb035c5a09c26b427f855fc00e818fe1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913358"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a><span data-ttu-id="220d3-102">Практическое руководство. Воспроизведение звука, хранящегося в виде ресурса, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="220d3-102">How to: Play a Sound Embedded in a Resource from a Windows Form</span></span>
<span data-ttu-id="220d3-103">Можно использовать <xref:System.Media.SoundPlayer> класс для воспроизведения звука из внедренного ресурса.</span><span class="sxs-lookup"><span data-stu-id="220d3-103">You can use the <xref:System.Media.SoundPlayer> class to play a sound from an embedded resource.</span></span>  
  
## <a name="example"></a><span data-ttu-id="220d3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="220d3-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Sound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="220d3-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="220d3-105">Compiling the Code</span></span>  
 <span data-ttu-id="220d3-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="220d3-106">This example requires:</span></span>  
  
 <span data-ttu-id="220d3-107">Импорт <xref:System.Media?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="220d3-107">Importing the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="220d3-108">включение звукового файла в качестве внедренного ресурса в проект;</span><span class="sxs-lookup"><span data-stu-id="220d3-108">Including the sound file as an embedded resource in your project.</span></span>  
  
 <span data-ttu-id="220d3-109">замена "\<AssemblyName>" именем сборки, в которую внедрен звуковой файл.</span><span class="sxs-lookup"><span data-stu-id="220d3-109">Replacing "\<AssemblyName>" with the name of the assembly in which the sound file is embedded.</span></span> <span data-ttu-id="220d3-110">Не включайте суффикс .dll.</span><span class="sxs-lookup"><span data-stu-id="220d3-110">Do not include the ".dll" suffix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="220d3-111">См. также</span><span class="sxs-lookup"><span data-stu-id="220d3-111">See also</span></span>

- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="220d3-112">Практическое руководство. Воспроизведение звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="220d3-112">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="220d3-113">Практическое руководство. Цикл звуков в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="220d3-113">How to: Loop a Sound Playing on a Windows Form</span></span>](how-to-loop-a-sound-playing-on-a-windows-form.md)
