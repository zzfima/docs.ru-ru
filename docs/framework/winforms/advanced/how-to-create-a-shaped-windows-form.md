---
title: "Практическое руководство. Создание фигурной формы Windows Forms"
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
- cpp
helpviewer_keywords:
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b0641adfcd7fa8e1d3367ea55d00830dd5a60706
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-shaped-windows-form"></a><span data-ttu-id="12321-102">Практическое руководство. Создание фигурной формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="12321-102">How to: Create a Shaped Windows Form</span></span>
<span data-ttu-id="12321-103">Этот пример создает форму эллипс, изменять размеры формы.</span><span class="sxs-lookup"><span data-stu-id="12321-103">This example gives a form an elliptical shape that resizes with the form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12321-104">Пример</span><span class="sxs-lookup"><span data-stu-id="12321-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="12321-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="12321-105">Compiling the Code</span></span>  
 <span data-ttu-id="12321-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="12321-106">This example requires:</span></span>  
  
-   <span data-ttu-id="12321-107">Ссылки на пространства имен <xref:System.Windows.Forms> и <xref:System.Drawing>.</span><span class="sxs-lookup"><span data-stu-id="12321-107">References to the <xref:System.Windows.Forms> and <xref:System.Drawing> namespaces.</span></span>  
  
 <span data-ttu-id="12321-108">В этом примере переопределяется <xref:System.Windows.Forms.Control.OnPaint%2A> метод, чтобы изменить фигуру формы.</span><span class="sxs-lookup"><span data-stu-id="12321-108">This example overrides the <xref:System.Windows.Forms.Control.OnPaint%2A> method to change the shape of the form.</span></span> <span data-ttu-id="12321-109">Чтобы использовать этот код, скопируйте в объявлении метода, а также код рисования внутри метода.</span><span class="sxs-lookup"><span data-stu-id="12321-109">To use this code, copy the method declaration as well as the drawing code inside the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12321-110">См. также</span><span class="sxs-lookup"><span data-stu-id="12321-110">See Also</span></span>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Drawing.Region>  
 <xref:System.Drawing>  
 <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>  
 <xref:System.Windows.Forms.Control.Region%2A>  
 [<span data-ttu-id="12321-111">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="12321-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
