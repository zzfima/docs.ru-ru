---
title: "Практическое руководство. Обрезка изображения по границам области обрезки"
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
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 281ae701bc3e5cee38952a05474360019f76a665
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-clipping-with-a-region"></a><span data-ttu-id="dffae-102">Практическое руководство. Обрезка изображения по границам области обрезки</span><span class="sxs-lookup"><span data-stu-id="dffae-102">How to: Use Clipping with a Region</span></span>
<span data-ttu-id="dffae-103">Одно из свойств объекта <xref:System.Drawing.Graphics> класс является отсеченную область.</span><span class="sxs-lookup"><span data-stu-id="dffae-103">One of the properties of the <xref:System.Drawing.Graphics> class is the clip region.</span></span> <span data-ttu-id="dffae-104">Все операции рисования, выполняемые данного <xref:System.Drawing.Graphics> ограничены областью обрезки данного объекта <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="dffae-104">All drawing done by a given <xref:System.Drawing.Graphics> object is restricted to the clip region of that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="dffae-105">Можно задать отсеченную область, вызвав <xref:System.Drawing.Graphics.SetClip%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="dffae-105">You can set the clip region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dffae-106">Пример</span><span class="sxs-lookup"><span data-stu-id="dffae-106">Example</span></span>  
 <span data-ttu-id="dffae-107">В следующем примере создается путь, состоящий из одного многоугольника.</span><span class="sxs-lookup"><span data-stu-id="dffae-107">The following example constructs a path that consists of a single polygon.</span></span> <span data-ttu-id="dffae-108">Затем код создает область, на основе этого пути.</span><span class="sxs-lookup"><span data-stu-id="dffae-108">Then the code constructs a region, based on that path.</span></span> <span data-ttu-id="dffae-109">Область передается в <xref:System.Drawing.Graphics.SetClip%2A> метод <xref:System.Drawing.Graphics> рисования объекта и затем двух строк.</span><span class="sxs-lookup"><span data-stu-id="dffae-109">The region is passed to the <xref:System.Drawing.Graphics.SetClip%2A> method of a <xref:System.Drawing.Graphics> object, and then two strings are drawn.</span></span>  
  
 <span data-ttu-id="dffae-110">На следующем рисунке обрезанные строки.</span><span class="sxs-lookup"><span data-stu-id="dffae-110">The following illustration shows the clipped strings.</span></span>  
  
 <span data-ttu-id="dffae-111">![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")</span><span class="sxs-lookup"><span data-stu-id="dffae-111">![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dffae-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="dffae-112">Compiling the Code</span></span>  
 <span data-ttu-id="dffae-113">Предыдущий пример кода предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="dffae-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dffae-114">См. также</span><span class="sxs-lookup"><span data-stu-id="dffae-114">See Also</span></span>  
 [<span data-ttu-id="dffae-115">Области в GDI+</span><span class="sxs-lookup"><span data-stu-id="dffae-115">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [<span data-ttu-id="dffae-116">Использование областей</span><span class="sxs-lookup"><span data-stu-id="dffae-116">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
