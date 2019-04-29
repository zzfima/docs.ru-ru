---
title: Практическое руководство. Поиск раскадровки в синхронном режиме
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- seeking Storyboards synchronously [WPF]
- Storyboards [WPF], seeking synchronously
ms.assetid: 03e06271-a946-4810-88ea-3fb4cfa9e0f1
ms.openlocfilehash: 8ac55346ac83ee94318de90655bde6053ef20687
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651237"
---
# <a name="how-to-seek-a-storyboard-synchronously"></a><span data-ttu-id="8b55c-102">Практическое руководство. Поиск раскадровки в синхронном режиме</span><span class="sxs-lookup"><span data-stu-id="8b55c-102">How to: Seek a Storyboard Synchronously</span></span>
<span data-ttu-id="8b55c-103">В следующем примере показано, как использовать <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A> метод <xref:System.Windows.Media.Animation.Storyboard> для поиска любой позиции в анимации раскадровки синхронно.</span><span class="sxs-lookup"><span data-stu-id="8b55c-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to seek to any position in a storyboard animation synchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b55c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8b55c-104">Example</span></span>  
 <span data-ttu-id="8b55c-105">Ниже приведена разметка XAML для примера.</span><span class="sxs-lookup"><span data-stu-id="8b55c-105">The following is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardSynchronouslyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml#seekstoryboardsynchronouslyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="8b55c-106">Пример</span><span class="sxs-lookup"><span data-stu-id="8b55c-106">Example</span></span>  
 <span data-ttu-id="8b55c-107">Ниже приведен код, используемый в приведенном выше коде XAML.</span><span class="sxs-lookup"><span data-stu-id="8b55c-107">The following is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml.cs#seekstoryboardsynchronouslycodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardSynchronouslyExample.xaml.vb#seekstoryboardsynchronouslycodebehindexamplewholepage)]
