---
title: Практическое руководство. Поиск раскадровки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], seeking
- seeking Storyboards [WPF]
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
ms.openlocfilehash: 7553550f406cc72603aa9f65e4233a13329223a9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354288"
---
# <a name="how-to-seek-a-storyboard"></a><span data-ttu-id="cadc3-102">Практическое руководство. Поиск раскадровки</span><span class="sxs-lookup"><span data-stu-id="cadc3-102">How to: Seek a Storyboard</span></span>
<span data-ttu-id="cadc3-103">В следующем примере показано, как использовать <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> метод <xref:System.Windows.Media.Animation.Storyboard> для перехода к любой позиции в анимации раскадровки.</span><span class="sxs-lookup"><span data-stu-id="cadc3-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to jump to any position in a storyboard animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cadc3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="cadc3-104">Example</span></span>  
 <span data-ttu-id="cadc3-105">Ниже приведена разметка XAML для примера.</span><span class="sxs-lookup"><span data-stu-id="cadc3-105">Below is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="cadc3-106">Пример</span><span class="sxs-lookup"><span data-stu-id="cadc3-106">Example</span></span>  
 <span data-ttu-id="cadc3-107">Ниже приведен код, используемый в приведенном выше коде XAML.</span><span class="sxs-lookup"><span data-stu-id="cadc3-107">Below is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="cadc3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="cadc3-108">See also</span></span>
- [<span data-ttu-id="cadc3-109">Поиск раскадровки в синхронном режиме</span><span class="sxs-lookup"><span data-stu-id="cadc3-109">Seek a Storyboard Synchronously</span></span>](how-to-seek-a-storyboard-synchronously.md)
