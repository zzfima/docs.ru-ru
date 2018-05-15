---
title: Практическое руководство. Связывание объектов растрового источника
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BitmapSource objects [WPF], chaining
- graphics [WPF], chaining BitmapSource objects
- chaining BitmapSource objects [WPF]
ms.assetid: 32d88853-395b-4855-9685-51a482a3b421
ms.openlocfilehash: 5c70b6ec132234959404203fb62567ddb0acf762
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-chain-bitmapsource-objects-together"></a><span data-ttu-id="f2877-102">Практическое руководство. Связывание объектов растрового источника</span><span class="sxs-lookup"><span data-stu-id="f2877-102">How to: Chain BitmapSource Objects Together</span></span>
<span data-ttu-id="f2877-103">В этом примере показано, как применять различные эффекты источник изображения с помощью цепочки из нескольких <xref:System.Windows.Media.Imaging.BitmapSource> производных объектов.</span><span class="sxs-lookup"><span data-stu-id="f2877-103">This example shows how you can apply a variety of effects to an image source by chaining multiple <xref:System.Windows.Media.Imaging.BitmapSource> derived objects together.</span></span>  
  
 <span data-ttu-id="f2877-104">Следующий пример использует цепочку, чтобы отразить и изменить формат пикселей источника изображения.</span><span class="sxs-lookup"><span data-stu-id="f2877-104">The following example uses chaining to flip and change the pixel format of the source of an image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2877-105">Пример</span><span class="sxs-lookup"><span data-stu-id="f2877-105">Example</span></span>  
 [!code-xaml[ImagingSnippetGallery_snip#ChainedBitmapSourcesXamlExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_snip/CS/ChainedBitmapSourcesExample.xaml#chainedbitmapsourcesxamlexamplewholepage)]  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/ChainedBitmapSourcesExample.cs#chainedbitmapsourcescodeexamplewholepage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/ChainedBitmapSourcesExample.vb#chainedbitmapsourcescodeexamplewholepage)]
