---
title: Практическое руководство. Обрезка изображения по границам области обрезки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: cf60b32df805a49f8da2760332dc32e34209f6dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163739"
---
# <a name="how-to-use-clipping-with-a-region"></a><span data-ttu-id="2608d-102">Практическое руководство. Обрезка изображения по границам области обрезки</span><span class="sxs-lookup"><span data-stu-id="2608d-102">How to: Use Clipping with a Region</span></span>
<span data-ttu-id="2608d-103">Одно из свойств объекта <xref:System.Drawing.Graphics> класс является отсеченную область.</span><span class="sxs-lookup"><span data-stu-id="2608d-103">One of the properties of the <xref:System.Drawing.Graphics> class is the clip region.</span></span> <span data-ttu-id="2608d-104">Все операции рисования, выполняемые заданного <xref:System.Drawing.Graphics> объекта будет ограничен отсеченную область объекта, <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="2608d-104">All drawing done by a given <xref:System.Drawing.Graphics> object is restricted to the clip region of that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="2608d-105">Можно задать отсеченную область, вызвав <xref:System.Drawing.Graphics.SetClip%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="2608d-105">You can set the clip region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2608d-106">Пример</span><span class="sxs-lookup"><span data-stu-id="2608d-106">Example</span></span>  
 <span data-ttu-id="2608d-107">В следующем примере создается путь, состоящий из одного многоугольника.</span><span class="sxs-lookup"><span data-stu-id="2608d-107">The following example constructs a path that consists of a single polygon.</span></span> <span data-ttu-id="2608d-108">Затем код создает область, на основе этого пути.</span><span class="sxs-lookup"><span data-stu-id="2608d-108">Then the code constructs a region, based on that path.</span></span> <span data-ttu-id="2608d-109">Область передается <xref:System.Drawing.Graphics.SetClip%2A> метод <xref:System.Drawing.Graphics> рисовании объекта и затем две строки.</span><span class="sxs-lookup"><span data-stu-id="2608d-109">The region is passed to the <xref:System.Drawing.Graphics.SetClip%2A> method of a <xref:System.Drawing.Graphics> object, and then two strings are drawn.</span></span>  
  
 <span data-ttu-id="2608d-110">Ниже показан усеченные строки.</span><span class="sxs-lookup"><span data-stu-id="2608d-110">The following illustration shows the clipped strings.</span></span>  
  
 <span data-ttu-id="2608d-111">![Клипов](./media/clip1.png "clip1")</span><span class="sxs-lookup"><span data-stu-id="2608d-111">![Clip](./media/clip1.png "clip1")</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2608d-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2608d-112">Compiling the Code</span></span>  
 <span data-ttu-id="2608d-113">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="2608d-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2608d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2608d-114">See also</span></span>

- [<span data-ttu-id="2608d-115">Области в GDI+</span><span class="sxs-lookup"><span data-stu-id="2608d-115">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="2608d-116">Использование областей</span><span class="sxs-lookup"><span data-stu-id="2608d-116">Using Regions</span></span>](using-regions.md)
