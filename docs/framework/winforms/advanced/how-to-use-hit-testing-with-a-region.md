---
title: "Практическое руководство. Проверка нахождения указателя мыши в заданной области"
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
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c0766c989df7c2329aa4d36af834378b02b1301
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="c5e75-102">Практическое руководство. Проверка нахождения указателя мыши в заданной области</span><span class="sxs-lookup"><span data-stu-id="c5e75-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="c5e75-103">Проверка на наличие предназначено, чтобы определить, является ли курсор над данным объектом, например значок или кнопки.</span><span class="sxs-lookup"><span data-stu-id="c5e75-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5e75-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c5e75-104">Example</span></span>  
 <span data-ttu-id="c5e75-105">В следующем примере создается область креста, являющаяся объединением двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="c5e75-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="c5e75-106">Предполагается, что переменная `point` содержит положение последнего щелчка.</span><span class="sxs-lookup"><span data-stu-id="c5e75-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="c5e75-107">Код проверяет, является ли `point` находится в регионе креста.</span><span class="sxs-lookup"><span data-stu-id="c5e75-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="c5e75-108">Если точка находится в области (есть попадание), она закрашивается непрозрачной красной кистью.</span><span class="sxs-lookup"><span data-stu-id="c5e75-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="c5e75-109">В противном случае она закрашивается полупрозрачной красной кистью.</span><span class="sxs-lookup"><span data-stu-id="c5e75-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c5e75-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c5e75-110">Compiling the Code</span></span>  
 <span data-ttu-id="c5e75-111">Предыдущий пример кода предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="c5e75-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e75-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c5e75-112">See Also</span></span>  
 <xref:System.Drawing.Region>  
 [<span data-ttu-id="c5e75-113">Области в GDI+</span><span class="sxs-lookup"><span data-stu-id="c5e75-113">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [<span data-ttu-id="c5e75-114">Практическое руководство. Обрезка изображения по границам области обрезки</span><span class="sxs-lookup"><span data-stu-id="c5e75-114">How to: Use Clipping with a Region</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
