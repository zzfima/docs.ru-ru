---
title: "Практическое руководство. Создание частной коллекции шрифтов"
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
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3016fb9a1b1d8466137bcaddb0b885c02c399baf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-private-font-collection"></a><span data-ttu-id="46500-102">Практическое руководство. Создание частной коллекции шрифтов</span><span class="sxs-lookup"><span data-stu-id="46500-102">How to: Create a Private Font Collection</span></span>
<span data-ttu-id="46500-103"><xref:System.Drawing.Text.PrivateFontCollection> Класс наследует от <xref:System.Drawing.Text.FontCollection> абстрактного базового класса.</span><span class="sxs-lookup"><span data-stu-id="46500-103">The <xref:System.Drawing.Text.PrivateFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="46500-104">Можно использовать <xref:System.Drawing.Text.PrivateFontCollection> объекта для сохранения набора шрифтов, предназначенных для конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="46500-104">You can use a <xref:System.Drawing.Text.PrivateFontCollection> object to maintain a set of fonts specifically for your application.</span></span> <span data-ttu-id="46500-105">Частной коллекции может включать шрифты установленной системы, а также шрифты, которые не были установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="46500-105">A private font collection can include installed system fonts as well as fonts that have not been installed on the computer.</span></span> <span data-ttu-id="46500-106">Чтобы добавить файл шрифта частной коллекции, вызовите <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> метод <xref:System.Drawing.Text.PrivateFontCollection> объекта.</span><span class="sxs-lookup"><span data-stu-id="46500-106">To add a font file to a private font collection, call the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> method of a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="46500-107"><xref:System.Drawing.Text.FontCollection.Families%2A> Свойство <xref:System.Drawing.Text.PrivateFontCollection> объект содержит массив <xref:System.Drawing.FontFamily> объектов.</span><span class="sxs-lookup"><span data-stu-id="46500-107">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of a <xref:System.Drawing.Text.PrivateFontCollection> object contains an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
 <span data-ttu-id="46500-108">Количество семейств шрифтов в частной коллекции не обязательно совпадает с количеством файлов шрифтов, которые были добавлены в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="46500-108">The number of font families in a private font collection is not necessarily the same as the number of font files that have been added to the collection.</span></span> <span data-ttu-id="46500-109">Например предположим, что файлы ArialBd.tff, Times.tff и TimesBd.tff добавить в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="46500-109">For example, suppose you add the files ArialBd.tff, Times.tff, and TimesBd.tff to a collection.</span></span> <span data-ttu-id="46500-110">Будет существовать три файла, но только два семейства в коллекции, так как Times.tff и TimesBd.tff относятся к одному семейству.</span><span class="sxs-lookup"><span data-stu-id="46500-110">There will be three files but only two families in the collection because Times.tff and TimesBd.tff belong to the same family.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46500-111">Пример</span><span class="sxs-lookup"><span data-stu-id="46500-111">Example</span></span>  
 <span data-ttu-id="46500-112">В следующем примере добавляется по следующим файлам три шрифта <xref:System.Drawing.Text.PrivateFontCollection> объекта:</span><span class="sxs-lookup"><span data-stu-id="46500-112">The following example adds the following three font files to a <xref:System.Drawing.Text.PrivateFontCollection> object:</span></span>  
  
-   <span data-ttu-id="46500-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, обычный)</span><span class="sxs-lookup"><span data-stu-id="46500-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, regular)</span></span>  
  
-   <span data-ttu-id="46500-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, полужирный курсив)</span><span class="sxs-lookup"><span data-stu-id="46500-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, bold italic)</span></span>  
  
-   <span data-ttu-id="46500-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, полужирный)</span><span class="sxs-lookup"><span data-stu-id="46500-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)</span></span>  
  
 <span data-ttu-id="46500-116">Этот код извлекает массив <xref:System.Drawing.FontFamily> объектов из <xref:System.Drawing.Text.FontCollection.Families%2A> свойство <xref:System.Drawing.Text.PrivateFontCollection> объекта.</span><span class="sxs-lookup"><span data-stu-id="46500-116">The code retrieves an array of <xref:System.Drawing.FontFamily> objects from the <xref:System.Drawing.Text.FontCollection.Families%2A> property of the <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="46500-117">Для каждого <xref:System.Drawing.FontFamily> объекта в коллекции, этот код вызывает <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> метод, чтобы определить, будут ли доступны различные стили (обычный, полужирный, курсив, полужирный курсив, подчеркнутый и зачеркнутый).</span><span class="sxs-lookup"><span data-stu-id="46500-117">For each <xref:System.Drawing.FontFamily> object in the collection, the code calls the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method to determine whether various styles (regular, bold, italic, bold italic, underline, and strikeout) are available.</span></span> <span data-ttu-id="46500-118">Аргументы, передаваемые <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> метод являются членами <xref:System.Drawing.FontStyle> перечисления.</span><span class="sxs-lookup"><span data-stu-id="46500-118">The arguments passed to the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method are members of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 <span data-ttu-id="46500-119">Если сочетание заданного семейства и стиля, <xref:System.Drawing.Font> объект создается с помощью этого семейства и стиля.</span><span class="sxs-lookup"><span data-stu-id="46500-119">If a given family/style combination is available, a <xref:System.Drawing.Font> object is constructed using that family and style.</span></span> <span data-ttu-id="46500-120">Первый аргумент, переданный <xref:System.Drawing.Font.%23ctor%2A> конструктор является имя семейства шрифтов (не <xref:System.Drawing.FontFamily> объекта, как в случае других вариантах <xref:System.Drawing.Font.%23ctor%2A> конструктора).</span><span class="sxs-lookup"><span data-stu-id="46500-120">The first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the font family name (not a <xref:System.Drawing.FontFamily> object as is the case for other variations of the <xref:System.Drawing.Font.%23ctor%2A> constructor).</span></span> <span data-ttu-id="46500-121">После <xref:System.Drawing.Font> объект создан, он передается <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> класса для отображения имени семейства вместе с именем стиля.</span><span class="sxs-lookup"><span data-stu-id="46500-121">After the <xref:System.Drawing.Font> object is constructed, it is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class to display the family name along with the name of the style.</span></span>  
  
 <span data-ttu-id="46500-122">Выходные данные приведенного ниже кода аналогична выходные данные, показанные на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="46500-122">The output of the following code is similar to the output shown in the following illustration.</span></span>  
  
 <span data-ttu-id="46500-123">![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")</span><span class="sxs-lookup"><span data-stu-id="46500-123">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")</span></span>  
  
 <span data-ttu-id="46500-124">Arial.tff (который добавлялся в частную коллекцию шрифтов в следующем примере кода) — это файл шрифта Arial обычного стиля.</span><span class="sxs-lookup"><span data-stu-id="46500-124">Arial.tff (which was added to the private font collection in the following code example) is the font file for the Arial regular style.</span></span> <span data-ttu-id="46500-125">Обратите внимание, что выходные данные программы отображает доступные стили отличный от обычной для семейства шрифтов Arial.</span><span class="sxs-lookup"><span data-stu-id="46500-125">Note, however, that the program output shows several available styles other than regular for the Arial font family.</span></span> <span data-ttu-id="46500-126">Причина этого заключается в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] может имитировать полужирный, курсив и полужирный курсив из обычного стиля.</span><span class="sxs-lookup"><span data-stu-id="46500-126">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold, italic, and bold italic styles from the regular style.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="46500-127">также можно создавать зачеркивание и подчеркивание обычного стиля.</span><span class="sxs-lookup"><span data-stu-id="46500-127"> can also produce underlines and strikeouts from the regular style.</span></span>  
  
 <span data-ttu-id="46500-128">Аналогичным образом [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] можно имитировать начертание полужирный курсив полужирный стиль или курсивное начертание.</span><span class="sxs-lookup"><span data-stu-id="46500-128">Similarly, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold italic style from either the bold style or the italic style.</span></span> <span data-ttu-id="46500-129">Выходные данные программы показывает, что начертание полужирный курсив доступно для семейства Times, хотя TimesBd.tff (Times New Roman, полужирный) является единственным файлом раз в коллекции.</span><span class="sxs-lookup"><span data-stu-id="46500-129">The program output shows that the bold italic style is available for the Times family even though TimesBd.tff (Times New Roman, bold) is the only Times file in the collection.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="46500-130">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="46500-130">Compiling the Code</span></span>  
 <span data-ttu-id="46500-131">Предыдущий пример кода предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="46500-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46500-132">См. также</span><span class="sxs-lookup"><span data-stu-id="46500-132">See Also</span></span>  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 [<span data-ttu-id="46500-133">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="46500-133">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
