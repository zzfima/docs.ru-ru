---
title: "Координаты Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ecb47efdd69730350cf98e1c7b1e49150ad324d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-coordinates"></a><span data-ttu-id="7f19e-102">Координаты Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f19e-102">Windows Forms Coordinates</span></span>
<span data-ttu-id="7f19e-103">Система координат для формы Windows Forms основана на координатах устройства, и основной единицей измерения при рисовании в формах Windows Forms является единица устройства (обычно точки).</span><span class="sxs-lookup"><span data-stu-id="7f19e-103">The coordinate system for a Windows Form is based on device coordinates, and the basic unit of measure when drawing in Windows Forms is the device unit (typically, the pixel).</span></span> <span data-ttu-id="7f19e-104">Точки на экране описываются парами координат x и y Координата x увеличивается вправо, а координата y увеличивается сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="7f19e-104">Points on the screen are described by x- and y-coordinate pairs, with the x-coordinates increasing to the right and the y-coordinates increasing from top to bottom.</span></span> <span data-ttu-id="7f19e-105">Расположение источника, относительно экрана, будет зависеть от указываются ли экранные или клиентские координаты.</span><span class="sxs-lookup"><span data-stu-id="7f19e-105">The location of the origin, relative to the screen, will vary depending on whether you are specifying screen or client coordinates.</span></span>  
  
## <a name="screen-coordinates"></a><span data-ttu-id="7f19e-106">Экранные координаты</span><span class="sxs-lookup"><span data-stu-id="7f19e-106">Screen Coordinates</span></span>  
 <span data-ttu-id="7f19e-107">Приложение Windows Forms указывает положение окна на экране в экранных координатах.</span><span class="sxs-lookup"><span data-stu-id="7f19e-107">A Windows Forms application specifies the position of a window on the screen in screen coordinates.</span></span> <span data-ttu-id="7f19e-108">Для экранные координаты находятся верхнего левого угла экрана.</span><span class="sxs-lookup"><span data-stu-id="7f19e-108">For screen coordinates, the origin is the upper-left corner of the screen.</span></span> <span data-ttu-id="7f19e-109">Полное положение окна часто описывается <xref:System.Drawing.Rectangle> структуры, содержащей экранные координаты двух точек, которые определяют верхний левый и правый нижний угол окна.</span><span class="sxs-lookup"><span data-stu-id="7f19e-109">The full position of a window is often described by a <xref:System.Drawing.Rectangle> structure containing the screen coordinates of two points that define the upper-left and lower-right corners of the window.</span></span>  
  
## <a name="client-coordinates"></a><span data-ttu-id="7f19e-110">Клиентские координаты</span><span class="sxs-lookup"><span data-stu-id="7f19e-110">Client Coordinates</span></span>  
 <span data-ttu-id="7f19e-111">Приложение Windows Forms указывает положение точек в формы или элемента управления с помощью клиентских координат.</span><span class="sxs-lookup"><span data-stu-id="7f19e-111">A Windows Forms application specifies the position of points in a form or control using client coordinates.</span></span> <span data-ttu-id="7f19e-112">Источником для клиентских координат является верхнего левого угла клиентской области элемента управления или формы.</span><span class="sxs-lookup"><span data-stu-id="7f19e-112">The origin for client coordinates is the upper-left corner of the client area of the control or form.</span></span> <span data-ttu-id="7f19e-113">Координаты клиента убедитесь, что приложение может использовать согласованные значения координат во время рисования в формы или элемента управления, независимо от положения формы или элемента управления на экране.</span><span class="sxs-lookup"><span data-stu-id="7f19e-113">Client coordinates ensure that an application can use consistent coordinate values while drawing in a form or control, regardless of the position of the form or control on the screen.</span></span>  
  
 <span data-ttu-id="7f19e-114">Размеры клиентской области также описываются <xref:System.Drawing.Rectangle> структуру, содержащую клиентские координаты области.</span><span class="sxs-lookup"><span data-stu-id="7f19e-114">The dimensions of the client area are also described by a <xref:System.Drawing.Rectangle> structure that contains client coordinates for the area.</span></span> <span data-ttu-id="7f19e-115">Во всех случаях координаты левого верхнего прямоугольника включается в клиентской области при исключении правая нижняя координата.</span><span class="sxs-lookup"><span data-stu-id="7f19e-115">In all cases, the upper-left coordinate of the rectangle is included in the client area, while the lower-right coordinate is excluded.</span></span> <span data-ttu-id="7f19e-116">Графические операции не включают правой и нижней границ клиентской области.</span><span class="sxs-lookup"><span data-stu-id="7f19e-116">Graphics operations do not include the right and lower edges of a client area.</span></span> <span data-ttu-id="7f19e-117">Например <xref:System.Drawing.Graphics.FillRectangle%2A> метод будет заполнить правой и нижней границ заданного прямоугольника, но не будет включать эти границы.</span><span class="sxs-lookup"><span data-stu-id="7f19e-117">For example the <xref:System.Drawing.Graphics.FillRectangle%2A> method will fill up to the right and lower edge of the specified rectangle, but will not include these edges.</span></span>  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a><span data-ttu-id="7f19e-118">Сопоставление одного типа координат</span><span class="sxs-lookup"><span data-stu-id="7f19e-118">Mapping From One Type of Coordinate to Another</span></span>  
 <span data-ttu-id="7f19e-119">В некоторых случаях может потребоваться сопоставить из экранных координат в клиентские координаты.</span><span class="sxs-lookup"><span data-stu-id="7f19e-119">Occasionally, you may need to map from screen coordinates to client coordinates.</span></span> <span data-ttu-id="7f19e-120">Это можно легко сделать с помощью <xref:System.Windows.Forms.Control.PointToClient%2A> и <xref:System.Windows.Forms.Control.PointToScreen%2A> методов, доступных в <xref:System.Windows.Forms.Control> класса.</span><span class="sxs-lookup"><span data-stu-id="7f19e-120">You can easily accomplish this by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available in the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="7f19e-121">Например <xref:System.Windows.Forms.Control.MousePosition%2A> свойство <xref:System.Windows.Forms.Control> сообщается в экранных координатах, но может потребоваться преобразовать их в клиентских координатах.</span><span class="sxs-lookup"><span data-stu-id="7f19e-121">For example, the <xref:System.Windows.Forms.Control.MousePosition%2A> property of <xref:System.Windows.Forms.Control> is reported in screen coordinates, but you may want to convert these to client coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f19e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7f19e-122">See Also</span></span>  
 <xref:System.Windows.Forms.Control.PointToClient%2A>  
 <xref:System.Windows.Forms.Control.PointToScreen%2A>
