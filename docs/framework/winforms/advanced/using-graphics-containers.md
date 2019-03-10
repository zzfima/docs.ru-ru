---
title: Использование графических контейнеров
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: cfad7254057a31ea8268784cd4b6849850f3e2aa
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704496"
---
# <a name="using-graphics-containers"></a><span data-ttu-id="96312-102">Использование графических контейнеров</span><span class="sxs-lookup"><span data-stu-id="96312-102">Using Graphics Containers</span></span>
<span data-ttu-id="96312-103">Объект <xref:System.Drawing.Graphics> объект предоставляет методы, такие как <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, и <xref:System.Drawing.Graphics.DrawString%2A> для отображения векторных изображений, растровых изображений и текста.</span><span class="sxs-lookup"><span data-stu-id="96312-103">A <xref:System.Drawing.Graphics> object provides methods such as <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, and <xref:System.Drawing.Graphics.DrawString%2A> for displaying vector images, raster images, and text.</span></span> <span data-ttu-id="96312-104">Объект <xref:System.Drawing.Graphics> объект также имеет несколько свойств, которые влияют на качество и ориентацию элементов, которые являются производными.</span><span class="sxs-lookup"><span data-stu-id="96312-104">A <xref:System.Drawing.Graphics> object also has several properties that influence the quality and orientation of the items that are drawn.</span></span> <span data-ttu-id="96312-105">Например свойство сглаживания режим определяет ли применять сглаживание к линии и кривые и влияет на свойство "преобразование" world, положения и поворота элементов, которые являются производными.</span><span class="sxs-lookup"><span data-stu-id="96312-105">For example, the smoothing mode property determines whether antialiasing is applied to lines and curves, and the world transformation property influences the position and rotation of the items that are drawn.</span></span>  
  
 <span data-ttu-id="96312-106">Объект <xref:System.Drawing.Graphics> связывается с конкретного устройства отображения.</span><span class="sxs-lookup"><span data-stu-id="96312-106">A <xref:System.Drawing.Graphics> object is associated with a particular display device.</span></span> <span data-ttu-id="96312-107">При использовании <xref:System.Drawing.Graphics> для рисования в окне <xref:System.Drawing.Graphics> объект также связан с этого конкретного окна.</span><span class="sxs-lookup"><span data-stu-id="96312-107">When you use a <xref:System.Drawing.Graphics> object to draw in a window, the <xref:System.Drawing.Graphics> object is also associated with that particular window.</span></span>  
  
 <span data-ttu-id="96312-108">Объект <xref:System.Drawing.Graphics> объект может рассматриваться как контейнер так как он содержит набор свойств, влияющих на отображение, и привязывается к конкретному устройству.</span><span class="sxs-lookup"><span data-stu-id="96312-108">A <xref:System.Drawing.Graphics> object can be thought of as a container because it holds a set of properties that influence drawing and it is linked to device-specific information.</span></span> <span data-ttu-id="96312-109">Можно создать дополнительный контейнер внутри существующего <xref:System.Drawing.Graphics> путем вызова метода <xref:System.Drawing.Graphics.BeginContainer%2A> , метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="96312-109">You can create a secondary container within an existing <xref:System.Drawing.Graphics> object by calling the <xref:System.Drawing.Graphics.BeginContainer%2A> method of that <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96312-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="96312-110">In This Section</span></span>  
 [<span data-ttu-id="96312-111">Управление состоянием графического объекта</span><span class="sxs-lookup"><span data-stu-id="96312-111">Managing the State of a Graphics Object</span></span>](managing-the-state-of-a-graphics-object.md)  
 <span data-ttu-id="96312-112">Описывает управление параметрами качества, области отсечения и преобразования <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="96312-112">Describes how manage the quality settings, clipping area and transformations of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [<span data-ttu-id="96312-113">Использование вложенных графических контейнеров</span><span class="sxs-lookup"><span data-stu-id="96312-113">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)  
 <span data-ttu-id="96312-114">Показано, как использование контейнеров для управления состоянием <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="96312-114">Shows how to use containers to control the state of the <xref:System.Drawing.Graphics> object.</span></span>
