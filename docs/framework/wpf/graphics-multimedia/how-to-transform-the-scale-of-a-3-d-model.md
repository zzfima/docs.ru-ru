---
title: Практическое руководство. Преобразование масштаба трехмерной модели
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: afe18cea95be945313ef78a690c58950a3fff9b0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378786"
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a><span data-ttu-id="dd3f9-102">Практическое руководство. Преобразование масштаба трехмерной модели</span><span class="sxs-lookup"><span data-stu-id="dd3f9-102">How to: Transform the Scale of a 3-D Model</span></span>
<span data-ttu-id="dd3f9-103">В этом примере показано, как масштабировать трехмерного объекта.</span><span class="sxs-lookup"><span data-stu-id="dd3f9-103">This example shows how to scale a 3-D object.</span></span> <span data-ttu-id="dd3f9-104">Чтобы увеличить трехмерного объекта, используйте <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span><span class="sxs-lookup"><span data-stu-id="dd3f9-104">To scale a 3-D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="dd3f9-105"><xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, И <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> свойства изменения размеров элемента с определенным коэффициентом.</span><span class="sxs-lookup"><span data-stu-id="dd3f9-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="dd3f9-106">Например <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> значение 1,5 объект увеличивается на 150 процентов от его исходной ширины.</span><span class="sxs-lookup"><span data-stu-id="dd3f9-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="dd3f9-107">Объект <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> значение 0,5 сжимает высоту объекта на 50 процентов.</span><span class="sxs-lookup"><span data-stu-id="dd3f9-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="dd3f9-108">В приведенном ниже коде показано использование <xref:System.Windows.Media.Media3D.ScaleTransform3D> как преобразование для <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="dd3f9-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="dd3f9-109">Пример</span><span class="sxs-lookup"><span data-stu-id="dd3f9-109">Example</span></span>  
 <span data-ttu-id="dd3f9-110">В следующем коде показано весь пример.</span><span class="sxs-lookup"><span data-stu-id="dd3f9-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="dd3f9-111">См. также</span><span class="sxs-lookup"><span data-stu-id="dd3f9-111">See also</span></span>
- [<span data-ttu-id="dd3f9-112">Анимация трехмерных преобразований</span><span class="sxs-lookup"><span data-stu-id="dd3f9-112">Animate 3-D Translations</span></span>](how-to-animate-3-d-translations.md)
- [<span data-ttu-id="dd3f9-113">Создание трехмерной сцены</span><span class="sxs-lookup"><span data-stu-id="dd3f9-113">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="dd3f9-114">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="dd3f9-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
