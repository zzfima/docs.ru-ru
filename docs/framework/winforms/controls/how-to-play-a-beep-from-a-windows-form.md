---
title: Практическое руководство. Воспроизведение сигнала в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
ms.openlocfilehash: 7fecc5d5b7259b743926713f87d9303596803582
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015812"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="a9edb-102">Практическое руководство. Воспроизведение сигнала в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9edb-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="a9edb-103">В этом примере воспроизводится звуковой сигнал во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a9edb-103">This example plays a beep at run time.</span></span>

## <a name="example"></a><span data-ttu-id="a9edb-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a9edb-104">Example</span></span>

```vb
Public Sub OnePing()
    Beep()
End Sub
```

```csharp
public void onePing()
{
    SystemSounds.Beep.Play();
}
```

> [!NOTE]
> <span data-ttu-id="a9edb-105">Звук, воспроизводимый C# в образце кода, определяется <xref:System.Media.SystemSounds.Beep%2A> параметром системный звук.</span><span class="sxs-lookup"><span data-stu-id="a9edb-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="a9edb-106">Дополнительные сведения см. в разделе <xref:System.Media.SystemSounds>.</span><span class="sxs-lookup"><span data-stu-id="a9edb-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="a9edb-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a9edb-107">Compiling the Code</span></span>
 <span data-ttu-id="a9edb-108">Для C#для этого примера требуется ссылка на <xref:System.Media?displayProperty=nameWithType> пространство имен.</span><span class="sxs-lookup"><span data-stu-id="a9edb-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9edb-109">См. также</span><span class="sxs-lookup"><span data-stu-id="a9edb-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="a9edb-110">Практическое руководство. Воспроизводить системный звук из формы Windows</span><span class="sxs-lookup"><span data-stu-id="a9edb-110">How to: Play a System Sound from a Windows Form</span></span>](how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="a9edb-111">Практическое руководство. Воспроизведение звука из формы Windows</span><span class="sxs-lookup"><span data-stu-id="a9edb-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
