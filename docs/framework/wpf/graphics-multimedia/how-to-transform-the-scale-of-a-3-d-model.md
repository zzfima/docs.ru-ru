---
title: 'Как: Преобразовать масштаб 3D-модели'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3D objects
- 3D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: be41a0e10929912c1b54bf7140d743d9453199bf
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111989"
---
# <a name="how-to-transform-the-scale-of-a-3d-model"></a><span data-ttu-id="26bfe-102">Как: Преобразовать масштаб 3D-модели</span><span class="sxs-lookup"><span data-stu-id="26bfe-102">How to: Transform the Scale of a 3D Model</span></span>
<span data-ttu-id="26bfe-103">В этом примере показано, как масштабировать 3D-объект.</span><span class="sxs-lookup"><span data-stu-id="26bfe-103">This example shows how to scale a 3D object.</span></span> <span data-ttu-id="26bfe-104">Для масштабирования 3D-объекта <xref:System.Windows.Media.Media3D.ScaleTransform3D>используйте.</span><span class="sxs-lookup"><span data-stu-id="26bfe-104">To scale a 3D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="26bfe-105">В <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> и свойства изменить размер элемента фактор, который вы указываете.</span><span class="sxs-lookup"><span data-stu-id="26bfe-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="26bfe-106">Например, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> значение 1,5 растягивает объект до 150 процентов от его первоначальной ширины.</span><span class="sxs-lookup"><span data-stu-id="26bfe-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="26bfe-107">Значение <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> 0,5 сжимает высоту объекта на 50 процентов.</span><span class="sxs-lookup"><span data-stu-id="26bfe-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="26bfe-108">Приведенный ниже код <xref:System.Windows.Media.Media3D.ScaleTransform3D> показывает использование <xref:System.Windows.Media.Media3D.GeometryModel3D>преобразования для .</span><span class="sxs-lookup"><span data-stu-id="26bfe-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="26bfe-109">Пример</span><span class="sxs-lookup"><span data-stu-id="26bfe-109">Example</span></span>  
 <span data-ttu-id="26bfe-110">Следующий код показывает весь образец.</span><span class="sxs-lookup"><span data-stu-id="26bfe-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="26bfe-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="26bfe-111">See also</span></span>

- [<span data-ttu-id="26bfe-112">Анимированные 3D переводы</span><span class="sxs-lookup"><span data-stu-id="26bfe-112">Animate 3D Translations</span></span>](how-to-animate-3-d-translations.md)
- [<span data-ttu-id="26bfe-113">Создание 3D-сцены</span><span class="sxs-lookup"><span data-stu-id="26bfe-113">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="26bfe-114">3D Графика Обзор</span><span class="sxs-lookup"><span data-stu-id="26bfe-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
