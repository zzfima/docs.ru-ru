---
title: Практическое руководство. Использование матрицы цветов для преобразования отдельного цвета
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 78fc498b0689026fb74ec0c422948c1879495560
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342860"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a><span data-ttu-id="3b101-102">Практическое руководство. Использование матрицы цветов для преобразования отдельного цвета</span><span class="sxs-lookup"><span data-stu-id="3b101-102">How to: Use a Color Matrix to Transform a Single Color</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="3b101-103">предоставляет <xref:System.Drawing.Image> и <xref:System.Drawing.Bitmap> классы для хранения и управления изображениями.</span><span class="sxs-lookup"><span data-stu-id="3b101-103">provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="3b101-104"><xref:System.Drawing.Image> и <xref:System.Drawing.Bitmap> объекты хранят цвет каждого пикселя как 32-разрядное число: 8 бит на красный, зеленый, синий и альфа-канала.</span><span class="sxs-lookup"><span data-stu-id="3b101-104"><xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects store the color of each pixel as a 32-bit number: 8 bits each for red, green, blue, and alpha.</span></span> <span data-ttu-id="3b101-105">Каждый из четырех компонентов является число от 0 до 255, где 0 соответствует нулевой интенсивности, а 255 — наибольшей интенсивности.</span><span class="sxs-lookup"><span data-stu-id="3b101-105">Each of the four components is a number from 0 through 255, with 0 representing no intensity and 255 representing full intensity.</span></span> <span data-ttu-id="3b101-106">Альфа-компонент определяет прозрачность цвета: 0 является полностью прозрачным, а 255 — полностью непрозрачный.</span><span class="sxs-lookup"><span data-stu-id="3b101-106">The alpha component specifies the transparency of the color: 0 is fully transparent, and 255 is fully opaque.</span></span>  
  
 <span data-ttu-id="3b101-107">Цветовой вектор является кортежем в форме (красный, зеленый, синий, альфа-версия).</span><span class="sxs-lookup"><span data-stu-id="3b101-107">A color vector is a 4-tuple of the form (red, green, blue, alpha).</span></span> <span data-ttu-id="3b101-108">Например вектор цвет (0, 255, 0, 255) представляет непрозрачный цвет, который не имеет красный и синий, а зеленый полная насыщенность.</span><span class="sxs-lookup"><span data-stu-id="3b101-108">For example, the color vector (0, 255, 0, 255) represents an opaque color that has no red or blue, but has green at full intensity.</span></span>  
  
 <span data-ttu-id="3b101-109">Другой способ представления цветов использует номер 1 для полной насыщенности.</span><span class="sxs-lookup"><span data-stu-id="3b101-109">Another convention for representing colors uses the number 1 for full intensity.</span></span> <span data-ttu-id="3b101-110">При использовании цвета, описанные в предыдущем абзаце будут представлены в вектор (0, 1, 0, 1).</span><span class="sxs-lookup"><span data-stu-id="3b101-110">Using that convention, the color described in the preceding paragraph would be represented by the vector (0, 1, 0, 1).</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="3b101-111">использует соглашение 1 как полной насыщенности, при преобразовании цветов.</span><span class="sxs-lookup"><span data-stu-id="3b101-111">uses the convention of 1 as full intensity when it performs color transformations.</span></span>  
  
 <span data-ttu-id="3b101-112">Линейные преобразования (поворот, масштабирование и т. п) можно применить в векторы цвета, умножив эти векторы матрицу 4 × 4.</span><span class="sxs-lookup"><span data-stu-id="3b101-112">You can apply linear transformations (rotation, scaling, and the like) to color vectors by multiplying the color vectors by a 4×4 matrix.</span></span> <span data-ttu-id="3b101-113">Тем не менее нельзя использовать матрицу 4 × 4, для выполнения преобразования (нелинейной).</span><span class="sxs-lookup"><span data-stu-id="3b101-113">However, you cannot use a 4×4 matrix to perform a translation (nonlinear).</span></span> <span data-ttu-id="3b101-114">Если добавить фиктивную пятую координату (например, номер 1) к каждому из цветовых векторов, можно использовать матрицу 5 × 5 для применения любое сочетание линейными преобразованиями и переводы.</span><span class="sxs-lookup"><span data-stu-id="3b101-114">If you add a dummy fifth coordinate (for example, the number 1) to each of the color vectors, you can use a 5×5 matrix to apply any combination of linear transformations and translations.</span></span> <span data-ttu-id="3b101-115">Преобразование, состоящее из линейного преобразования, а затем перевод называется аффинные преобразования.</span><span class="sxs-lookup"><span data-stu-id="3b101-115">A transformation consisting of a linear transformation followed by a translation is called an affine transformation.</span></span>  
  
 <span data-ttu-id="3b101-116">Например предположим, что вы хотите начать с цветом (0,2, 0,0, 0,4, 1,0) и применить следующие преобразования:</span><span class="sxs-lookup"><span data-stu-id="3b101-116">For example, suppose you want to start with the color (0.2, 0.0, 0.4, 1.0) and apply the following transformations:</span></span>  
  
1. <span data-ttu-id="3b101-117">Double красного компонента</span><span class="sxs-lookup"><span data-stu-id="3b101-117">Double the red component</span></span>  
  
2. <span data-ttu-id="3b101-118">Добавить 0,2 к компонентам красного, зеленого и синего</span><span class="sxs-lookup"><span data-stu-id="3b101-118">Add 0.2 to the red, green, and blue components</span></span>  
  
 <span data-ttu-id="3b101-119">Следующие Перемножение матриц выполнит эти два преобразования в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="3b101-119">The following matrix multiplication will perform the pair of transformations in the order listed.</span></span>  
  
 <span data-ttu-id="3b101-120">![Перекрашивание](./media/recoloring01.gif "recoloring01")</span><span class="sxs-lookup"><span data-stu-id="3b101-120">![Recoloring](./media/recoloring01.gif "recoloring01")</span></span>  
  
 <span data-ttu-id="3b101-121">Элементы матрицы цветов индексируются (начинающийся с нуля), строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="3b101-121">The elements of a color matrix are indexed (zero-based) by row and then column.</span></span> <span data-ttu-id="3b101-122">Например запись в пятой строке и третьем столбце матрицы M обозначается M [4] [2].</span><span class="sxs-lookup"><span data-stu-id="3b101-122">For example, the entry in the fifth row and third column of matrix M is denoted by M[4][2].</span></span>  
  
 <span data-ttu-id="3b101-123">5 × 5 единичной матрицей (показано на следующем рисунке) имеет единицы на диагонали и размерностью.</span><span class="sxs-lookup"><span data-stu-id="3b101-123">The 5×5 identity matrix (shown in the following illustration) has 1s on the diagonal and 0s everywhere else.</span></span> <span data-ttu-id="3b101-124">При умножении вектора на единичную матрицу, цвет не изменяется.</span><span class="sxs-lookup"><span data-stu-id="3b101-124">If you multiply a color vector by the identity matrix, the color vector does not change.</span></span> <span data-ttu-id="3b101-125">Начать с единичной матрицы и внесите небольшое изменение, которое формирует нужные преобразования — удобный способ создания матрицы преобразования цветов.</span><span class="sxs-lookup"><span data-stu-id="3b101-125">A convenient way to form the matrix of a color transformation is to start with the identity matrix and make a small change that produces the desired transformation.</span></span>  
  
 <span data-ttu-id="3b101-126">![Перекрашивание](./media/recoloring02.gif "recoloring02")</span><span class="sxs-lookup"><span data-stu-id="3b101-126">![Recoloring](./media/recoloring02.gif "recoloring02")</span></span>  
  
 <span data-ttu-id="3b101-127">Более подробное описание матрицы и преобразований, см. в разделе [системы координат и преобразования](coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="3b101-127">For a more detailed discussion of matrices and transformations, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b101-128">Пример</span><span class="sxs-lookup"><span data-stu-id="3b101-128">Example</span></span>  
 <span data-ttu-id="3b101-129">В следующем примере выполняются образ, который был только один цвет (0,2, 0,0, 0,4, 1.0) и применяется преобразование, описанное выше.</span><span class="sxs-lookup"><span data-stu-id="3b101-129">The following example takes an image that is all one color (0.2, 0.0, 0.4, 1.0) and applies the transformation described in the preceding paragraphs.</span></span>  
  
 <span data-ttu-id="3b101-130">Ниже показан исходное изображение в левой части и преобразованные изображения справа.</span><span class="sxs-lookup"><span data-stu-id="3b101-130">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="3b101-131">![Цвета](./media/colortrans1.png "colortrans1")</span><span class="sxs-lookup"><span data-stu-id="3b101-131">![Colors](./media/colortrans1.png "colortrans1")</span></span>  
  
 <span data-ttu-id="3b101-132">В следующем примере код выполняет указанные ниже действия для выполнения гамме:</span><span class="sxs-lookup"><span data-stu-id="3b101-132">The code in the following example uses the following steps to perform the recoloring:</span></span>  
  
1. <span data-ttu-id="3b101-133">Инициализировать <xref:System.Drawing.Imaging.ColorMatrix> объекта.</span><span class="sxs-lookup"><span data-stu-id="3b101-133">Initialize a <xref:System.Drawing.Imaging.ColorMatrix> object.</span></span>  
  
2. <span data-ttu-id="3b101-134">Создание <xref:System.Drawing.Imaging.ImageAttributes> и передать <xref:System.Drawing.Imaging.ColorMatrix> объект <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> метод <xref:System.Drawing.Imaging.ImageAttributes> объекта.</span><span class="sxs-lookup"><span data-stu-id="3b101-134">Create an <xref:System.Drawing.Imaging.ImageAttributes> object and pass the <xref:System.Drawing.Imaging.ColorMatrix> object to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object.</span></span>  
  
3. <span data-ttu-id="3b101-135">Передайте <xref:System.Drawing.Imaging.ImageAttributes> объект <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="3b101-135">Pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3b101-136">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3b101-136">Compiling the Code</span></span>  
 <span data-ttu-id="3b101-137">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="3b101-137">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b101-138">См. также</span><span class="sxs-lookup"><span data-stu-id="3b101-138">See also</span></span>

- [<span data-ttu-id="3b101-139">перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="3b101-139">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="3b101-140">Системы координат и преобразования</span><span class="sxs-lookup"><span data-stu-id="3b101-140">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
