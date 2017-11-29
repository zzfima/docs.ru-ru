---
title: "Использование графических контейнеров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 337057e10e03712aa93b00d9c687374e53f8dd03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="using-graphics-containers"></a><span data-ttu-id="a7d78-102">Использование графических контейнеров</span><span class="sxs-lookup"><span data-stu-id="a7d78-102">Using Graphics Containers</span></span>
<span data-ttu-id="a7d78-103">Объект <xref:System.Drawing.Graphics> объект предоставляет методы, такие как <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, и <xref:System.Drawing.Graphics.DrawString%2A> для отображения векторных изображений, растровые изображения и текст.</span><span class="sxs-lookup"><span data-stu-id="a7d78-103">A <xref:System.Drawing.Graphics> object provides methods such as <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, and <xref:System.Drawing.Graphics.DrawString%2A> for displaying vector images, raster images, and text.</span></span> <span data-ttu-id="a7d78-104">Объект <xref:System.Drawing.Graphics> также имеет несколько свойств, которые влияют на качество и ориентацию элементов, которые являются производными.</span><span class="sxs-lookup"><span data-stu-id="a7d78-104">A <xref:System.Drawing.Graphics> object also has several properties that influence the quality and orientation of the items that are drawn.</span></span> <span data-ttu-id="a7d78-105">Например свойство режим сглаживания определяет ли применять сглаживание к прямых и кривых линий, а свойство преобразования world влияет положения и поворота элементов, которые являются производными.</span><span class="sxs-lookup"><span data-stu-id="a7d78-105">For example, the smoothing mode property determines whether antialiasing is applied to lines and curves, and the world transformation property influences the position and rotation of the items that are drawn.</span></span>  
  
 <span data-ttu-id="a7d78-106">Объект <xref:System.Drawing.Graphics> объект связан с конкретного устройства отображения.</span><span class="sxs-lookup"><span data-stu-id="a7d78-106">A <xref:System.Drawing.Graphics> object is associated with a particular display device.</span></span> <span data-ttu-id="a7d78-107">При использовании <xref:System.Drawing.Graphics> для рисования в окне <xref:System.Drawing.Graphics> объекта также привязывается к рассматриваемому окну.</span><span class="sxs-lookup"><span data-stu-id="a7d78-107">When you use a <xref:System.Drawing.Graphics> object to draw in a window, the <xref:System.Drawing.Graphics> object is also associated with that particular window.</span></span>  
  
 <span data-ttu-id="a7d78-108">Объект <xref:System.Drawing.Graphics> объект можно рассматривать как контейнер, так как она содержит набор параметров, влияющих на отображение, и привязывается к конкретному устройству.</span><span class="sxs-lookup"><span data-stu-id="a7d78-108">A <xref:System.Drawing.Graphics> object can be thought of as a container because it holds a set of properties that influence drawing and it is linked to device-specific information.</span></span> <span data-ttu-id="a7d78-109">Можно создать вторичный контейнер внутри существующего <xref:System.Drawing.Graphics> путем вызова метода <xref:System.Drawing.Graphics.BeginContainer%2A> , метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="a7d78-109">You can create a secondary container within an existing <xref:System.Drawing.Graphics> object by calling the <xref:System.Drawing.Graphics.BeginContainer%2A> method of that <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7d78-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="a7d78-110">In This Section</span></span>  
 [<span data-ttu-id="a7d78-111">Управление состоянием графического объекта</span><span class="sxs-lookup"><span data-stu-id="a7d78-111">Managing the State of a Graphics Object</span></span>](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 <span data-ttu-id="a7d78-112">Описывает способ управления параметрами качества, областью обрезки и преобразования <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="a7d78-112">Describes how manage the quality settings, clipping area and transformations of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [<span data-ttu-id="a7d78-113">Использование вложенных графических контейнеров</span><span class="sxs-lookup"><span data-stu-id="a7d78-113">Using Nested Graphics Containers</span></span>](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 <span data-ttu-id="a7d78-114">Показано, как использовать контейнеры для контроля состояния <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="a7d78-114">Shows how to use containers to control the state of the <xref:System.Drawing.Graphics> object.</span></span>
