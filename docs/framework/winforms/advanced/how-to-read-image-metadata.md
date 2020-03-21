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
ms.openlocfilehash: e2b56175e625281a920c390e5feb4238e3cb7f44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182521"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="a4bcc-102">Практическое руководство. Чтение метаданных изображения</span><span class="sxs-lookup"><span data-stu-id="a4bcc-102">How to: Read Image Metadata</span></span>

<span data-ttu-id="a4bcc-103">Некоторые файлы изображений содержат метаданные, которые можно прочитать для определения особенностей изображения.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="a4bcc-104">Например, цифровая фотография может содержать метаданные, которые можно прочитать, чтобы определить модель камеры, используемой для захвата изображения.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="a4bcc-105">С помощью GDI можно читать существующие метаданные, а также писать новые метаданные в файлы изображений.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>

<span data-ttu-id="a4bcc-106">GDI хранит отдельный фрагмент метаданных <xref:System.Drawing.Imaging.PropertyItem> в объекте.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="a4bcc-107">Вы можете <xref:System.Drawing.Image.PropertyItems%2A> прочитать <xref:System.Drawing.Image> свойство объекта для извлечения всех метаданных из файла.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="a4bcc-108">Свойство <xref:System.Drawing.Image.PropertyItems%2A> возвращает массив <xref:System.Drawing.Imaging.PropertyItem> объектов.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>

<span data-ttu-id="a4bcc-109">Объект <xref:System.Drawing.Imaging.PropertyItem> имеет следующие четыре `Id` `Value`свойства: , , `Len`и `Type`.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>

## <a name="id"></a><span data-ttu-id="a4bcc-110">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="a4bcc-110">Id</span></span>

<span data-ttu-id="a4bcc-111">Тег, идентифицирующие элемент метаданных.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="a4bcc-112">Некоторые значения, которым можно <xref:System.Drawing.Imaging.PropertyItem.Id%2A> присвоить, отображаются в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="a4bcc-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table:</span></span>

|<span data-ttu-id="a4bcc-113">Гексадецимальная ценность</span><span class="sxs-lookup"><span data-stu-id="a4bcc-113">Hexadecimal value</span></span>|<span data-ttu-id="a4bcc-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a4bcc-114">Description</span></span>|
|-----------------------|-----------------|
|<span data-ttu-id="a4bcc-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="a4bcc-115">0x0320</span></span><br /><br /> <span data-ttu-id="a4bcc-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="a4bcc-116">0x010F</span></span><br /><br /> <span data-ttu-id="a4bcc-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="a4bcc-117">0x0110</span></span><br /><br /> <span data-ttu-id="a4bcc-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="a4bcc-118">0x9003</span></span><br /><br /> <span data-ttu-id="a4bcc-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="a4bcc-119">0x829A</span></span><br /><br /> <span data-ttu-id="a4bcc-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="a4bcc-120">0x5090</span></span><br /><br /> <span data-ttu-id="a4bcc-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="a4bcc-121">0x5091</span></span>|<span data-ttu-id="a4bcc-122">Название изображения</span><span class="sxs-lookup"><span data-stu-id="a4bcc-122">Image title</span></span><br /><br /> <span data-ttu-id="a4bcc-123">Производитель оборудования</span><span class="sxs-lookup"><span data-stu-id="a4bcc-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="a4bcc-124">Модель оборудования</span><span class="sxs-lookup"><span data-stu-id="a4bcc-124">Equipment model</span></span><br /><br /> <span data-ttu-id="a4bcc-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="a4bcc-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="a4bcc-126">Время экспозиции Exif</span><span class="sxs-lookup"><span data-stu-id="a4bcc-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="a4bcc-127">Таблица luminance</span><span class="sxs-lookup"><span data-stu-id="a4bcc-127">Luminance table</span></span><br /><br /> <span data-ttu-id="a4bcc-128">Хроминас стол</span><span class="sxs-lookup"><span data-stu-id="a4bcc-128">Chrominance table</span></span>|

## <a name="value"></a><span data-ttu-id="a4bcc-129">Значение</span><span class="sxs-lookup"><span data-stu-id="a4bcc-129">Value</span></span>

<span data-ttu-id="a4bcc-130">Массив значений типа .</span><span class="sxs-lookup"><span data-stu-id="a4bcc-130">An array of values.</span></span> <span data-ttu-id="a4bcc-131">Формат значений определяется <xref:System.Drawing.Imaging.PropertyItem.Type%2A> свойством.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>

## <a name="len"></a><span data-ttu-id="a4bcc-132">Len</span><span class="sxs-lookup"><span data-stu-id="a4bcc-132">Len</span></span>

<span data-ttu-id="a4bcc-133">Длина (в байтах) массива значений, <xref:System.Drawing.Imaging.PropertyItem.Value%2A> на которые указывает свойство.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>

## <a name="type"></a><span data-ttu-id="a4bcc-134">Тип</span><span class="sxs-lookup"><span data-stu-id="a4bcc-134">Type</span></span>

<span data-ttu-id="a4bcc-135">Тип данных значений в массиве, `Value` на который указывает свойство.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="a4bcc-136">Форматы, указанные `Type` значениями свойств, отображаются в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="a4bcc-136">The formats indicated by the `Type` property values are shown in the following table:</span></span>

|<span data-ttu-id="a4bcc-137">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="a4bcc-137">Numeric value</span></span>|<span data-ttu-id="a4bcc-138">Описание</span><span class="sxs-lookup"><span data-stu-id="a4bcc-138">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="a4bcc-139">1</span><span class="sxs-lookup"><span data-stu-id="a4bcc-139">1</span></span>|<span data-ttu-id="a4bcc-140">`Byte`;</span><span class="sxs-lookup"><span data-stu-id="a4bcc-140">A `Byte`</span></span>|
|<span data-ttu-id="a4bcc-141">2</span><span class="sxs-lookup"><span data-stu-id="a4bcc-141">2</span></span>|<span data-ttu-id="a4bcc-142">Массив объектов, кодированных `Byte` как ASCII</span><span class="sxs-lookup"><span data-stu-id="a4bcc-142">An array of `Byte` objects encoded as ASCII</span></span>|
|<span data-ttu-id="a4bcc-143">3</span><span class="sxs-lookup"><span data-stu-id="a4bcc-143">3</span></span>|<span data-ttu-id="a4bcc-144">16-битный ряд</span><span class="sxs-lookup"><span data-stu-id="a4bcc-144">A 16-bit integer</span></span>|
|<span data-ttu-id="a4bcc-145">4</span><span class="sxs-lookup"><span data-stu-id="a4bcc-145">4</span></span>|<span data-ttu-id="a4bcc-146">32-битный ряд</span><span class="sxs-lookup"><span data-stu-id="a4bcc-146">A 32-bit integer</span></span>|
|<span data-ttu-id="a4bcc-147">5</span><span class="sxs-lookup"><span data-stu-id="a4bcc-147">5</span></span>|<span data-ttu-id="a4bcc-148">Массив из `Byte` двух объектов, представляющих рациональное число</span><span class="sxs-lookup"><span data-stu-id="a4bcc-148">An array of two `Byte` objects that represent a rational number</span></span>|
|<span data-ttu-id="a4bcc-149">6</span><span class="sxs-lookup"><span data-stu-id="a4bcc-149">6</span></span>|<span data-ttu-id="a4bcc-150">Не используется</span><span class="sxs-lookup"><span data-stu-id="a4bcc-150">Not used</span></span>|
|<span data-ttu-id="a4bcc-151">7</span><span class="sxs-lookup"><span data-stu-id="a4bcc-151">7</span></span>|<span data-ttu-id="a4bcc-152">Не определено.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-152">Undefined</span></span>|
|<span data-ttu-id="a4bcc-153">8</span><span class="sxs-lookup"><span data-stu-id="a4bcc-153">8</span></span>|<span data-ttu-id="a4bcc-154">Не используется</span><span class="sxs-lookup"><span data-stu-id="a4bcc-154">Not used</span></span>|
|<span data-ttu-id="a4bcc-155">9</span><span class="sxs-lookup"><span data-stu-id="a4bcc-155">9</span></span>|`SLong`|
|<span data-ttu-id="a4bcc-156">10</span><span class="sxs-lookup"><span data-stu-id="a4bcc-156">10</span></span>|`SRational`|

## <a name="example"></a><span data-ttu-id="a4bcc-157">Пример</span><span class="sxs-lookup"><span data-stu-id="a4bcc-157">Example</span></span>
  
<span data-ttu-id="a4bcc-158">Следующий пример кода читает и отображает семь фрагментов `FakePhoto.jpg`метаданных в файле.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-158">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="a4bcc-159">Второй (индекс 1) элемент свойства <xref:System.Drawing.Imaging.PropertyItem.Id%2A> в списке имеет 0x010F (производитель оборудования) и <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-кодированный байт массив).</span><span class="sxs-lookup"><span data-stu-id="a4bcc-159">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="a4bcc-160">Пример кода отображает значение этого элемента свойства.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-160">The code example displays the value of that property item.</span></span>

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

<span data-ttu-id="a4bcc-161">Код производит выход, аналогичный следующим:</span><span class="sxs-lookup"><span data-stu-id="a4bcc-161">The code produces output similar to the following:</span></span>

```output
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

## <a name="compiling-the-code"></a><span data-ttu-id="a4bcc-162">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a4bcc-162">Compiling the Code</span></span>

<span data-ttu-id="a4bcc-163">Предыдущий пример предназначен для использования с формами Windows, и он требует, <xref:System.Windows.Forms.PaintEventArgs> `e`который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-163">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="a4bcc-164">Обвязайте <xref:System.Windows.Forms.Control.Paint> событие формы и вставьте этот код в обработчик события краски.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-164">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="a4bcc-165">Необходимо заменить `FakePhoto.jpg` имя изображения и траекторию, действительную в вашей системе, и импортировать пространство `System.Drawing.Imaging` имен.</span><span class="sxs-lookup"><span data-stu-id="a4bcc-165">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4bcc-166">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a4bcc-166">See also</span></span>

- [<span data-ttu-id="a4bcc-167">Изображения, Bitmaps и Метафайлы</span><span class="sxs-lookup"><span data-stu-id="a4bcc-167">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="a4bcc-168">Работа с растровыми и векторными изображениями</span><span class="sxs-lookup"><span data-stu-id="a4bcc-168">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
