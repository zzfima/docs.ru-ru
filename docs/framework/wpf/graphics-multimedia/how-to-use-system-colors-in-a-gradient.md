---
title: Практическое руководство. Использование системных цветов в градиенте
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 3148a5901ccf64194717e26664ab8b9cbd57db2a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365962"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="0d4d2-102">Практическое руководство. Использование системных цветов в градиенте</span><span class="sxs-lookup"><span data-stu-id="0d4d2-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="0d4d2-103">Чтобы использовать системный цвет в градиенте, используйте  *\<SystemColor >* цвет и  *\<SystemColor >* ColorKey статические свойства класса <xref:System.Windows.SystemColors> для получения ссылки на цвет, где  *\<SystemColor >* имя требуемого системного цвета.</span><span class="sxs-lookup"><span data-stu-id="0d4d2-103">To use a system color in a gradient, you use the *\<SystemColor>* Color and *\<SystemColor>* ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="0d4d2-104">Используйте  *\<SystemColor >* свойства ColorKey, если вы хотите создать динамическую ссылку, которая обновляется автоматически по мере изменения темы системы.</span><span class="sxs-lookup"><span data-stu-id="0d4d2-104">Use the *\<SystemColor>* ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="0d4d2-105">В противном случае используйте  *\<SystemColor >* свойства цветов.</span><span class="sxs-lookup"><span data-stu-id="0d4d2-105">Otherwise, use the *\<SystemColor>* Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d4d2-106">Пример</span><span class="sxs-lookup"><span data-stu-id="0d4d2-106">Example</span></span>  
 <span data-ttu-id="0d4d2-107">В следующем примере для создания градиента используются динамические ресурсы системных цветов.</span><span class="sxs-lookup"><span data-stu-id="0d4d2-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="0d4d2-108">В следующем примере для создания градиента используются статические ресурсы системных цветов.</span><span class="sxs-lookup"><span data-stu-id="0d4d2-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0d4d2-109">См. также</span><span class="sxs-lookup"><span data-stu-id="0d4d2-109">See also</span></span>
- <xref:System.Windows.SystemColors>
- [<span data-ttu-id="0d4d2-110">Заливка области с помощью системной кисти</span><span class="sxs-lookup"><span data-stu-id="0d4d2-110">Paint an Area with a System Brush</span></span>](how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="0d4d2-111">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="0d4d2-111">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
