---
title: Практическое руководство. Чтение метаданных изображения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 0a53e9b9d23c03715bf3088a4ae8577a39527995
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173619"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="cb534-102">Практическое руководство. Чтение метаданных изображения</span><span class="sxs-lookup"><span data-stu-id="cb534-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="cb534-103">Некоторые файлы изображений содержат метаданные, которые можно прочитать, чтобы определить возможности изображения.</span><span class="sxs-lookup"><span data-stu-id="cb534-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="cb534-104">Например цифровой фотографии может содержать метаданные, которые можно прочитать, чтобы определить марки и модели фотоаппарата, использованного для создания образа.</span><span class="sxs-lookup"><span data-stu-id="cb534-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="cb534-105">С помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], можно считывать существующие метаданные, и можно также добавлять новые метаданные в файлы изображений.</span><span class="sxs-lookup"><span data-stu-id="cb534-105">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="cb534-106">хранит каждый отдельный блок метаданных в <xref:System.Drawing.Imaging.PropertyItem> объекта.</span><span class="sxs-lookup"><span data-stu-id="cb534-106">stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="cb534-107">Можно прочитать <xref:System.Drawing.Image.PropertyItems%2A> свойство <xref:System.Drawing.Image> объекта для извлечения метаданных из файла.</span><span class="sxs-lookup"><span data-stu-id="cb534-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="cb534-108"><xref:System.Drawing.Image.PropertyItems%2A> Свойство возвращает массив <xref:System.Drawing.Imaging.PropertyItem> объектов.</span><span class="sxs-lookup"><span data-stu-id="cb534-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="cb534-109">Объект <xref:System.Drawing.Imaging.PropertyItem> имеет следующие четыре свойства: `Id`, `Value`, `Len`, и `Type`.</span><span class="sxs-lookup"><span data-stu-id="cb534-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="cb534-110">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="cb534-110">Id</span></span>  
 <span data-ttu-id="cb534-111">Тег, определяющий элемент метаданных.</span><span class="sxs-lookup"><span data-stu-id="cb534-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="cb534-112">Некоторые значения, которые могут быть назначены <xref:System.Drawing.Imaging.PropertyItem.Id%2A> показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="cb534-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="cb534-113">Шестнадцатеричное значение</span><span class="sxs-lookup"><span data-stu-id="cb534-113">Hexadecimal value</span></span>|<span data-ttu-id="cb534-114">Описание</span><span class="sxs-lookup"><span data-stu-id="cb534-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="cb534-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="cb534-115">0x0320</span></span><br /><br /> <span data-ttu-id="cb534-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="cb534-116">0x010F</span></span><br /><br /> <span data-ttu-id="cb534-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="cb534-117">0x0110</span></span><br /><br /> <span data-ttu-id="cb534-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="cb534-118">0x9003</span></span><br /><br /> <span data-ttu-id="cb534-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="cb534-119">0x829A</span></span><br /><br /> <span data-ttu-id="cb534-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="cb534-120">0x5090</span></span><br /><br /> <span data-ttu-id="cb534-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="cb534-121">0x5091</span></span>|<span data-ttu-id="cb534-122">Изображение заголовка</span><span class="sxs-lookup"><span data-stu-id="cb534-122">Image title</span></span><br /><br /> <span data-ttu-id="cb534-123">Поставщик вычислительной техники</span><span class="sxs-lookup"><span data-stu-id="cb534-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="cb534-124">Модель оборудования</span><span class="sxs-lookup"><span data-stu-id="cb534-124">Equipment model</span></span><br /><br /> <span data-ttu-id="cb534-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="cb534-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="cb534-126">Время выдержки EXIF</span><span class="sxs-lookup"><span data-stu-id="cb534-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="cb534-127">Таблицы освещенности</span><span class="sxs-lookup"><span data-stu-id="cb534-127">Luminance table</span></span><br /><br /> <span data-ttu-id="cb534-128">Таблицы цветности</span><span class="sxs-lookup"><span data-stu-id="cb534-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="cb534-129">Значение</span><span class="sxs-lookup"><span data-stu-id="cb534-129">Value</span></span>  
 <span data-ttu-id="cb534-130">Массив значений.</span><span class="sxs-lookup"><span data-stu-id="cb534-130">An array of values.</span></span> <span data-ttu-id="cb534-131">Формат значений определяется <xref:System.Drawing.Imaging.PropertyItem.Type%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="cb534-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="cb534-132">Len</span><span class="sxs-lookup"><span data-stu-id="cb534-132">Len</span></span>  
 <span data-ttu-id="cb534-133">Размер (в байтах) массив значений, на который указывает <xref:System.Drawing.Imaging.PropertyItem.Value%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="cb534-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="cb534-134">Тип</span><span class="sxs-lookup"><span data-stu-id="cb534-134">Type</span></span>  
 <span data-ttu-id="cb534-135">Тип значений в массиве, на который указывает `Value` свойство.</span><span class="sxs-lookup"><span data-stu-id="cb534-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="cb534-136">Типы, определяемые по `Type` в следующей таблице показаны значения свойств</span><span class="sxs-lookup"><span data-stu-id="cb534-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="cb534-137">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="cb534-137">Numeric value</span></span>|<span data-ttu-id="cb534-138">Описание</span><span class="sxs-lookup"><span data-stu-id="cb534-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="cb534-139">1</span><span class="sxs-lookup"><span data-stu-id="cb534-139">1</span></span>|<span data-ttu-id="cb534-140">А</span><span class="sxs-lookup"><span data-stu-id="cb534-140">A</span></span> `Byte`|  
|<span data-ttu-id="cb534-141">2</span><span class="sxs-lookup"><span data-stu-id="cb534-141">2</span></span>|<span data-ttu-id="cb534-142">Массив `Byte` объекты в кодировке ASCII</span><span class="sxs-lookup"><span data-stu-id="cb534-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="cb534-143">3</span><span class="sxs-lookup"><span data-stu-id="cb534-143">3</span></span>|<span data-ttu-id="cb534-144">16-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="cb534-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="cb534-145">4</span><span class="sxs-lookup"><span data-stu-id="cb534-145">4</span></span>|<span data-ttu-id="cb534-146">32-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="cb534-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="cb534-147">5</span><span class="sxs-lookup"><span data-stu-id="cb534-147">5</span></span>|<span data-ttu-id="cb534-148">Массив из двух `Byte` объекты, представляющие рациональное число</span><span class="sxs-lookup"><span data-stu-id="cb534-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="cb534-149">6</span><span class="sxs-lookup"><span data-stu-id="cb534-149">6</span></span>|<span data-ttu-id="cb534-150">Не используется</span><span class="sxs-lookup"><span data-stu-id="cb534-150">Not used</span></span>|  
|<span data-ttu-id="cb534-151">7</span><span class="sxs-lookup"><span data-stu-id="cb534-151">7</span></span>|<span data-ttu-id="cb534-152">Не определено</span><span class="sxs-lookup"><span data-stu-id="cb534-152">Undefined</span></span>|  
|<span data-ttu-id="cb534-153">8</span><span class="sxs-lookup"><span data-stu-id="cb534-153">8</span></span>|<span data-ttu-id="cb534-154">Не используется</span><span class="sxs-lookup"><span data-stu-id="cb534-154">Not used</span></span>|  
|<span data-ttu-id="cb534-155">9</span><span class="sxs-lookup"><span data-stu-id="cb534-155">9</span></span>|`SLong`|  
|<span data-ttu-id="cb534-156">10</span><span class="sxs-lookup"><span data-stu-id="cb534-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="cb534-157">Пример</span><span class="sxs-lookup"><span data-stu-id="cb534-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cb534-158">Описание</span><span class="sxs-lookup"><span data-stu-id="cb534-158">Description</span></span>  
 <span data-ttu-id="cb534-159">В следующем примере кода считывает и отображает семи блоков метаданных в файле `FakePhoto.jpg`.</span><span class="sxs-lookup"><span data-stu-id="cb534-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="cb534-160">Второй элемент свойства (индекс 1) в списке <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (производитель) и <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (массив байтов в кодировке ASCII).</span><span class="sxs-lookup"><span data-stu-id="cb534-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="cb534-161">В примере кода отображает значение данного свойства.</span><span class="sxs-lookup"><span data-stu-id="cb534-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="cb534-162">В коде создается результат, аналогичный приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="cb534-162">The code produces output similar to the following:</span></span>  
  
 `Property Item 0`  
  
 `id: 0x320`  
  
 `type: 2`  
  
 `length: 16 bytes`  
  
 `Property Item 1`  
  
 `id: 0x10f`  
  
 `type: 2`  
  
 `length: 17 bytes`  
  
 `Property Item 2`  
  
 `id: 0x110`  
  
 `type: 2`  
  
 `length: 7 bytes`  
  
 `Property Item 3`  
  
 `id: 0x9003`  
  
 `type: 2`  
  
 `length: 20 bytes`  
  
 `Property Item 4`  
  
 `id: 0x829a`  
  
 `type: 5`  
  
 `length: 8 bytes`  
  
 `Property Item 5`  
  
 `id: 0x5090`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `Property Item 6`  
  
 `id: 0x5091`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `The equipment make is Northwind Camera.`  
  
### <a name="code"></a><span data-ttu-id="cb534-163">Код</span><span class="sxs-lookup"><span data-stu-id="cb534-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cb534-164">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="cb534-164">Compiling the Code</span></span>  
 <span data-ttu-id="cb534-165">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="cb534-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="cb534-166">Обработка формы <xref:System.Windows.Forms.Control.Paint> событий и вставьте этот код в обработчик событий paint.</span><span class="sxs-lookup"><span data-stu-id="cb534-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="cb534-167">Необходимо заменить `FakePhoto.jpg` допустимы для системы и импорта путь и имя образа `System.Drawing.Imaging` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cb534-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb534-168">См. также</span><span class="sxs-lookup"><span data-stu-id="cb534-168">See also</span></span>

- [<span data-ttu-id="cb534-169">Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile</span><span class="sxs-lookup"><span data-stu-id="cb534-169">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="cb534-170">Работа с растровыми и векторными изображениями</span><span class="sxs-lookup"><span data-stu-id="cb534-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
