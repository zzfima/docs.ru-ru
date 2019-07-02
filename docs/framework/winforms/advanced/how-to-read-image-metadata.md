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
ms.openlocfilehash: 6c02f7e5744828fd8eddc88be8d7da28f3bc2a2a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505776"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="29d1d-102">Практическое руководство. Чтение метаданных изображения</span><span class="sxs-lookup"><span data-stu-id="29d1d-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="29d1d-103">Некоторые файлы изображений содержат метаданные, которые можно прочитать, чтобы определить возможности изображения.</span><span class="sxs-lookup"><span data-stu-id="29d1d-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="29d1d-104">Например цифровой фотографии может содержать метаданные, которые можно прочитать, чтобы определить марки и модели фотоаппарата, использованного для создания образа.</span><span class="sxs-lookup"><span data-stu-id="29d1d-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="29d1d-105">С помощью GDI + можно считывать существующие метаданные, и можно также добавлять новые метаданные в файлы изображений.</span><span class="sxs-lookup"><span data-stu-id="29d1d-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 <span data-ttu-id="29d1d-106">GDI + хранит каждый отдельный блок метаданных в <xref:System.Drawing.Imaging.PropertyItem> объекта.</span><span class="sxs-lookup"><span data-stu-id="29d1d-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="29d1d-107">Можно прочитать <xref:System.Drawing.Image.PropertyItems%2A> свойство <xref:System.Drawing.Image> объекта для извлечения метаданных из файла.</span><span class="sxs-lookup"><span data-stu-id="29d1d-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="29d1d-108"><xref:System.Drawing.Image.PropertyItems%2A> Свойство возвращает массив <xref:System.Drawing.Imaging.PropertyItem> объектов.</span><span class="sxs-lookup"><span data-stu-id="29d1d-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="29d1d-109">Объект <xref:System.Drawing.Imaging.PropertyItem> имеет следующие четыре свойства: `Id`, `Value`, `Len`, и `Type`.</span><span class="sxs-lookup"><span data-stu-id="29d1d-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="29d1d-110">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="29d1d-110">Id</span></span>  
 <span data-ttu-id="29d1d-111">Тег, определяющий элемент метаданных.</span><span class="sxs-lookup"><span data-stu-id="29d1d-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="29d1d-112">Некоторые значения, которые могут быть назначены <xref:System.Drawing.Imaging.PropertyItem.Id%2A> показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="29d1d-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="29d1d-113">Шестнадцатеричное значение</span><span class="sxs-lookup"><span data-stu-id="29d1d-113">Hexadecimal value</span></span>|<span data-ttu-id="29d1d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="29d1d-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="29d1d-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="29d1d-115">0x0320</span></span><br /><br /> <span data-ttu-id="29d1d-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="29d1d-116">0x010F</span></span><br /><br /> <span data-ttu-id="29d1d-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="29d1d-117">0x0110</span></span><br /><br /> <span data-ttu-id="29d1d-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="29d1d-118">0x9003</span></span><br /><br /> <span data-ttu-id="29d1d-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="29d1d-119">0x829A</span></span><br /><br /> <span data-ttu-id="29d1d-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="29d1d-120">0x5090</span></span><br /><br /> <span data-ttu-id="29d1d-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="29d1d-121">0x5091</span></span>|<span data-ttu-id="29d1d-122">Изображение заголовка</span><span class="sxs-lookup"><span data-stu-id="29d1d-122">Image title</span></span><br /><br /> <span data-ttu-id="29d1d-123">Поставщик вычислительной техники</span><span class="sxs-lookup"><span data-stu-id="29d1d-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="29d1d-124">Модель оборудования</span><span class="sxs-lookup"><span data-stu-id="29d1d-124">Equipment model</span></span><br /><br /> <span data-ttu-id="29d1d-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="29d1d-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="29d1d-126">Время выдержки EXIF</span><span class="sxs-lookup"><span data-stu-id="29d1d-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="29d1d-127">Таблицы освещенности</span><span class="sxs-lookup"><span data-stu-id="29d1d-127">Luminance table</span></span><br /><br /> <span data-ttu-id="29d1d-128">Таблицы цветности</span><span class="sxs-lookup"><span data-stu-id="29d1d-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="29d1d-129">Значение</span><span class="sxs-lookup"><span data-stu-id="29d1d-129">Value</span></span>  
 <span data-ttu-id="29d1d-130">Массив значений.</span><span class="sxs-lookup"><span data-stu-id="29d1d-130">An array of values.</span></span> <span data-ttu-id="29d1d-131">Формат значений определяется <xref:System.Drawing.Imaging.PropertyItem.Type%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="29d1d-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="29d1d-132">Len</span><span class="sxs-lookup"><span data-stu-id="29d1d-132">Len</span></span>  
 <span data-ttu-id="29d1d-133">Размер (в байтах) массив значений, на который указывает <xref:System.Drawing.Imaging.PropertyItem.Value%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="29d1d-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="29d1d-134">Тип</span><span class="sxs-lookup"><span data-stu-id="29d1d-134">Type</span></span>  
 <span data-ttu-id="29d1d-135">Тип значений в массиве, на который указывает `Value` свойство.</span><span class="sxs-lookup"><span data-stu-id="29d1d-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="29d1d-136">Типы, определяемые по `Type` в следующей таблице показаны значения свойств</span><span class="sxs-lookup"><span data-stu-id="29d1d-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="29d1d-137">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="29d1d-137">Numeric value</span></span>|<span data-ttu-id="29d1d-138">Описание</span><span class="sxs-lookup"><span data-stu-id="29d1d-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="29d1d-139">1</span><span class="sxs-lookup"><span data-stu-id="29d1d-139">1</span></span>|<span data-ttu-id="29d1d-140">`Byte`</span><span class="sxs-lookup"><span data-stu-id="29d1d-140">A `Byte`</span></span>|  
|<span data-ttu-id="29d1d-141">2</span><span class="sxs-lookup"><span data-stu-id="29d1d-141">2</span></span>|<span data-ttu-id="29d1d-142">Массив `Byte` объекты в кодировке ASCII</span><span class="sxs-lookup"><span data-stu-id="29d1d-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="29d1d-143">3</span><span class="sxs-lookup"><span data-stu-id="29d1d-143">3</span></span>|<span data-ttu-id="29d1d-144">16-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="29d1d-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="29d1d-145">4</span><span class="sxs-lookup"><span data-stu-id="29d1d-145">4</span></span>|<span data-ttu-id="29d1d-146">32-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="29d1d-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="29d1d-147">5</span><span class="sxs-lookup"><span data-stu-id="29d1d-147">5</span></span>|<span data-ttu-id="29d1d-148">Массив из двух `Byte` объекты, представляющие рациональное число</span><span class="sxs-lookup"><span data-stu-id="29d1d-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="29d1d-149">6</span><span class="sxs-lookup"><span data-stu-id="29d1d-149">6</span></span>|<span data-ttu-id="29d1d-150">Не используется</span><span class="sxs-lookup"><span data-stu-id="29d1d-150">Not used</span></span>|  
|<span data-ttu-id="29d1d-151">7</span><span class="sxs-lookup"><span data-stu-id="29d1d-151">7</span></span>|<span data-ttu-id="29d1d-152">Не определено</span><span class="sxs-lookup"><span data-stu-id="29d1d-152">Undefined</span></span>|  
|<span data-ttu-id="29d1d-153">8</span><span class="sxs-lookup"><span data-stu-id="29d1d-153">8</span></span>|<span data-ttu-id="29d1d-154">Не используется</span><span class="sxs-lookup"><span data-stu-id="29d1d-154">Not used</span></span>|  
|<span data-ttu-id="29d1d-155">9</span><span class="sxs-lookup"><span data-stu-id="29d1d-155">9</span></span>|`SLong`|  
|<span data-ttu-id="29d1d-156">10</span><span class="sxs-lookup"><span data-stu-id="29d1d-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="29d1d-157">Пример</span><span class="sxs-lookup"><span data-stu-id="29d1d-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="29d1d-158">Описание</span><span class="sxs-lookup"><span data-stu-id="29d1d-158">Description</span></span>  
 <span data-ttu-id="29d1d-159">В следующем примере кода считывает и отображает семи блоков метаданных в файле `FakePhoto.jpg`.</span><span class="sxs-lookup"><span data-stu-id="29d1d-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="29d1d-160">Второй элемент свойства (индекс 1) в списке <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (производитель) и <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (массив байтов в кодировке ASCII).</span><span class="sxs-lookup"><span data-stu-id="29d1d-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="29d1d-161">В примере кода отображает значение данного свойства.</span><span class="sxs-lookup"><span data-stu-id="29d1d-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="29d1d-162">В коде создается результат, аналогичный приведенному ниже:</span><span class="sxs-lookup"><span data-stu-id="29d1d-162">The code produces output similar to the following:</span></span>  
 
```
 Property Item 0
  
 id: 0x320
  
 type: 2
 
 length: 16 bytes 
  
 Property Item 1
  
 id: 0x10f
  
 type: 2 
  
 length: 17 bytes
  
 Property Item 2
  
 id: 0x110
  
 type: 2
  
 length: 7 bytes
  
 Property Item 3
  
 id: 0x9003
  
 type: 2
  
 length: 20 bytes
  
 Property Item 4
  
 id: 0x829a
  
 type: 5
  
 length: 8 bytes
  
 Property Item 5
  
 id: 0x5090
  
 type: 3
  
 length: 128 bytes
  
 Property Item 6
  
 id: 0x5091
  
 type: 3
  
 length: 128 bytes
  
 The equipment make is Northwind Camera.
 ```
  
### <a name="code"></a><span data-ttu-id="29d1d-163">Код</span><span class="sxs-lookup"><span data-stu-id="29d1d-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="29d1d-164">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="29d1d-164">Compiling the Code</span></span>  
 <span data-ttu-id="29d1d-165">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="29d1d-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="29d1d-166">Обработка формы <xref:System.Windows.Forms.Control.Paint> событий и вставьте этот код в обработчик событий paint.</span><span class="sxs-lookup"><span data-stu-id="29d1d-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="29d1d-167">Необходимо заменить `FakePhoto.jpg` допустимы для системы и импорта путь и имя образа `System.Drawing.Imaging` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="29d1d-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d1d-168">См. также</span><span class="sxs-lookup"><span data-stu-id="29d1d-168">See also</span></span>

- [<span data-ttu-id="29d1d-169">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="29d1d-169">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="29d1d-170">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="29d1d-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
