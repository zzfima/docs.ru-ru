---
title: Практическое руководство. Преобразование цветов изображения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 04e61383ef79b17ea6e1523588cd9593ec9b082c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954633"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="f8816-102">Практическое руководство. Преобразование цветов изображения</span><span class="sxs-lookup"><span data-stu-id="f8816-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="f8816-103">Перевод добавляет значение к одному или нескольким из четырех компонентов цвета.</span><span class="sxs-lookup"><span data-stu-id="f8816-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="f8816-104">В следующей таблице приведены элементы матрицы цветов, представляющих переводы.</span><span class="sxs-lookup"><span data-stu-id="f8816-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="f8816-105">Преобразуемый компонент</span><span class="sxs-lookup"><span data-stu-id="f8816-105">Component to be translated</span></span>|<span data-ttu-id="f8816-106">Элемент матрицы</span><span class="sxs-lookup"><span data-stu-id="f8816-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="f8816-107">Красный</span><span class="sxs-lookup"><span data-stu-id="f8816-107">Red</span></span>|<span data-ttu-id="f8816-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="f8816-108">[4][0]</span></span>|  
|<span data-ttu-id="f8816-109">Зеленый</span><span class="sxs-lookup"><span data-stu-id="f8816-109">Green</span></span>|<span data-ttu-id="f8816-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="f8816-110">[4][1]</span></span>|  
|<span data-ttu-id="f8816-111">Синий</span><span class="sxs-lookup"><span data-stu-id="f8816-111">Blue</span></span>|<span data-ttu-id="f8816-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="f8816-112">[4][2]</span></span>|  
|<span data-ttu-id="f8816-113">Коэффициент альфа</span><span class="sxs-lookup"><span data-stu-id="f8816-113">Alpha</span></span>|<span data-ttu-id="f8816-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="f8816-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f8816-115">Пример</span><span class="sxs-lookup"><span data-stu-id="f8816-115">Example</span></span>  
 <span data-ttu-id="f8816-116">В следующем примере создается <xref:System.Drawing.Image> объекта из файла ColorBars.bmp.</span><span class="sxs-lookup"><span data-stu-id="f8816-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="f8816-117">Затем код добавляет 0,75 красного компонента каждого пикселя в изображении.</span><span class="sxs-lookup"><span data-stu-id="f8816-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="f8816-118">Исходное изображение отображается вместе с преобразованные изображения.</span><span class="sxs-lookup"><span data-stu-id="f8816-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="f8816-119">Ниже показан исходное изображение в левой части и преобразованные изображения справа:</span><span class="sxs-lookup"><span data-stu-id="f8816-119">The following illustration shows the original image on the left and the transformed image on the right:</span></span>  
  
 ![Снимок экрана исходные и преобразованные изображения.](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 <span data-ttu-id="f8816-121">Ниже перечислены эти векторы четырех полос до и после преобразования.</span><span class="sxs-lookup"><span data-stu-id="f8816-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="f8816-122">Обратите внимание на то, что так как максимальное значение для компонента цвета равно 1, красный компонент во второй строке остается неизменным.</span><span class="sxs-lookup"><span data-stu-id="f8816-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="f8816-123">(Аналогичным образом, минимальное значение для компонента цвета — 0).</span><span class="sxs-lookup"><span data-stu-id="f8816-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="f8816-124">До преобразования</span><span class="sxs-lookup"><span data-stu-id="f8816-124">Original</span></span>|<span data-ttu-id="f8816-125">Перевод</span><span class="sxs-lookup"><span data-stu-id="f8816-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="f8816-126">Черный (0, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="f8816-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="f8816-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="f8816-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="f8816-128">Красный (1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="f8816-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="f8816-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="f8816-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="f8816-130">Зеленый (0, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="f8816-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="f8816-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="f8816-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="f8816-132">Синий (0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="f8816-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="f8816-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="f8816-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8816-134">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f8816-134">Compiling the Code</span></span>  
 <span data-ttu-id="f8816-135">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика события <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="f8816-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f8816-136">Замените `ColorBars.bmp` в вашей системе путь и имя файла изображения.</span><span class="sxs-lookup"><span data-stu-id="f8816-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8816-137">См. также</span><span class="sxs-lookup"><span data-stu-id="f8816-137">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="f8816-138">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8816-138">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f8816-139">перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="f8816-139">Recoloring Images</span></span>](recoloring-images.md)
