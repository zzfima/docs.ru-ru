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
ms.workload: dotnet
ms.openlocfilehash: 90b0c2748960443c0d63d22b33566ebcb2b4545b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a><span data-ttu-id="e5f9a-102">Практическое руководство. Воспроизведение звука, хранящегося в виде ресурса, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5f9a-102">How to: Play a Sound Embedded in a Resource from a Windows Form</span></span>
<span data-ttu-id="e5f9a-103">Можно использовать <xref:System.Media.SoundPlayer> класса для воспроизведения звука из внедренного ресурса.</span><span class="sxs-lookup"><span data-stu-id="e5f9a-103">You can use the <xref:System.Media.SoundPlayer> class to play a sound from an embedded resource.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5f9a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e5f9a-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e5f9a-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e5f9a-105">Compiling the Code</span></span>  
 <span data-ttu-id="e5f9a-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="e5f9a-106">This example requires:</span></span>  
  
 <span data-ttu-id="e5f9a-107">Импорт <xref:System.Media?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e5f9a-107">Importing the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="e5f9a-108">включение звукового файла в качестве внедренного ресурса в проект;</span><span class="sxs-lookup"><span data-stu-id="e5f9a-108">Including the sound file as an embedded resource in your project.</span></span>  
  
 <span data-ttu-id="e5f9a-109">замена "\<AssemblyName>" именем сборки, в которую внедрен звуковой файл.</span><span class="sxs-lookup"><span data-stu-id="e5f9a-109">Replacing "\<AssemblyName>" with the name of the assembly in which the sound file is embedded.</span></span> <span data-ttu-id="e5f9a-110">Не включайте суффикс .dll.</span><span class="sxs-lookup"><span data-stu-id="e5f9a-110">Do not include the ".dll" suffix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f9a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e5f9a-111">See Also</span></span>  
 <xref:System.Media.SoundPlayer>  
 [<span data-ttu-id="e5f9a-112">Практическое руководство. Воспроизведение звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5f9a-112">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 [<span data-ttu-id="e5f9a-113">Практическое руководство. Циклическое воспроизведение звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5f9a-113">How to: Loop a Sound Playing on a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)
