---
title: Практическое руководство. Использование таблицы перераспределения цветов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 360ec30563ee5001d784dc7c4ccdb50563867c29
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505762"
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="dd8c4-102">Практическое руководство. Использование таблицы перераспределения цветов</span><span class="sxs-lookup"><span data-stu-id="dd8c4-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="dd8c4-103">Преобразование — это процесс преобразования цветов в изображении в соответствии с таблицей сопоставления цветов.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="dd8c4-104">Таблицы преобразования цветов представляет собой массив <xref:System.Drawing.Imaging.ColorMap> объектов.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="dd8c4-105">Каждый <xref:System.Drawing.Imaging.ColorMap> объект в массиве имеет <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> свойство и <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="dd8c4-106">Когда GDI + Рисует изображение, каждый пиксель изображения сравнивается с массив старых цветов.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-106">When GDI+ draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="dd8c4-107">Если цвет пикселя совпадает со старым цветом, его цвет изменяется на соответствующий новый цвет.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="dd8c4-108">Цвета изменяются только для подготовки к просмотру — значения цвета самого изображения (хранящиеся в <xref:System.Drawing.Image> или <xref:System.Drawing.Bitmap> объекта), не изменяются.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="dd8c4-109">Чтобы нарисовать пересопоставленный изображение, инициализируйте массив <xref:System.Drawing.Imaging.ColorMap> объектов.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="dd8c4-110">Передайте массив <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> метод <xref:System.Drawing.Imaging.ImageAttributes> , а затем передать <xref:System.Drawing.Imaging.ImageAttributes> объект <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd8c4-111">Пример</span><span class="sxs-lookup"><span data-stu-id="dd8c4-111">Example</span></span>  
 <span data-ttu-id="dd8c4-112">В следующем примере создается <xref:System.Drawing.Image> объекта из файла RemapInput.bmp.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="dd8c4-113">Код создает таблицу преобразования цветов, состоящий из одного <xref:System.Drawing.Imaging.ColorMap> объекта.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="dd8c4-114"><xref:System.Drawing.Imaging.ColorMap.OldColor%2A> Свойство `ColorRemap` объекта отображается красным цветом, а <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> свойство имеет значение blue.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="dd8c4-115">Изображение будет рисоваться один раз без изменения сопоставления и один раз с повторное сопоставление.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="dd8c4-116">В процессе преобразования все Красные пиксели на синий.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="dd8c4-117">Ниже показан исходное изображение в левой части и преобразованное изображение справа.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 ![Снимок экрана, показывающий исходного изображения, а преобразованное изображение.](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dd8c4-119">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="dd8c4-119">Compiling the Code</span></span>  
 <span data-ttu-id="dd8c4-120">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="dd8c4-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd8c4-121">См. также</span><span class="sxs-lookup"><span data-stu-id="dd8c4-121">See also</span></span>

- [<span data-ttu-id="dd8c4-122">перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="dd8c4-122">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="dd8c4-123">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="dd8c4-123">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
