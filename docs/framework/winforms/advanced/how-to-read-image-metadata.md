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
ms.openlocfilehash: cd3b636f8f0058d4a8eacc656f95d5f46b8967e2
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040755"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="a43df-102">Практическое руководство. Чтение метаданных изображения</span><span class="sxs-lookup"><span data-stu-id="a43df-102">How to: Read Image Metadata</span></span>

<span data-ttu-id="a43df-103">Некоторые файлы изображений содержат метаданные, которые можно прочитать, чтобы определить характеристики изображения.</span><span class="sxs-lookup"><span data-stu-id="a43df-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="a43df-104">Например, цифровая фотография может содержать метаданные, которые можно прочитать для определения марки и модели камеры, используемой для записи образа.</span><span class="sxs-lookup"><span data-stu-id="a43df-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="a43df-105">С помощью GDI+ можно считывать существующие метаданные, а также записывать новые метаданные в файлы изображений.</span><span class="sxs-lookup"><span data-stu-id="a43df-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>

<span data-ttu-id="a43df-106">GDI+ сохраняет отдельный фрагмент метаданных в объекте <xref:System.Drawing.Imaging.PropertyItem>.</span><span class="sxs-lookup"><span data-stu-id="a43df-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="a43df-107">Можно прочитать свойство <xref:System.Drawing.Image.PropertyItems%2A> объекта <xref:System.Drawing.Image>, чтобы получить все метаданные из файла.</span><span class="sxs-lookup"><span data-stu-id="a43df-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="a43df-108">Свойство <xref:System.Drawing.Image.PropertyItems%2A> возвращает массив объектов <xref:System.Drawing.Imaging.PropertyItem>.</span><span class="sxs-lookup"><span data-stu-id="a43df-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>

<span data-ttu-id="a43df-109">Объект <xref:System.Drawing.Imaging.PropertyItem> имеет следующие четыре свойства: `Id`, `Value`, `Len`и `Type`.</span><span class="sxs-lookup"><span data-stu-id="a43df-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>

## <a name="id"></a><span data-ttu-id="a43df-110">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="a43df-110">Id</span></span>

<span data-ttu-id="a43df-111">Тег, определяющий элемент метаданных.</span><span class="sxs-lookup"><span data-stu-id="a43df-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="a43df-112">Некоторые значения, которые могут быть назначены <xref:System.Drawing.Imaging.PropertyItem.Id%2A>, показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a43df-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table:</span></span>

|<span data-ttu-id="a43df-113">Шестнадцатеричное значение</span><span class="sxs-lookup"><span data-stu-id="a43df-113">Hexadecimal value</span></span>|<span data-ttu-id="a43df-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a43df-114">Description</span></span>|
|-----------------------|-----------------|
|<span data-ttu-id="a43df-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="a43df-115">0x0320</span></span><br /><br /> <span data-ttu-id="a43df-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="a43df-116">0x010F</span></span><br /><br /> <span data-ttu-id="a43df-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="a43df-117">0x0110</span></span><br /><br /> <span data-ttu-id="a43df-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="a43df-118">0x9003</span></span><br /><br /> <span data-ttu-id="a43df-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="a43df-119">0x829A</span></span><br /><br /> <span data-ttu-id="a43df-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="a43df-120">0x5090</span></span><br /><br /> <span data-ttu-id="a43df-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="a43df-121">0x5091</span></span>|<span data-ttu-id="a43df-122">Название образа</span><span class="sxs-lookup"><span data-stu-id="a43df-122">Image title</span></span><br /><br /> <span data-ttu-id="a43df-123">Производитель оборудования</span><span class="sxs-lookup"><span data-stu-id="a43df-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="a43df-124">Модель оборудования</span><span class="sxs-lookup"><span data-stu-id="a43df-124">Equipment model</span></span><br /><br /> <span data-ttu-id="a43df-125">ексифдторигинал</span><span class="sxs-lookup"><span data-stu-id="a43df-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="a43df-126">Время экспозиции EXIF</span><span class="sxs-lookup"><span data-stu-id="a43df-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="a43df-127">Таблица освещенности</span><span class="sxs-lookup"><span data-stu-id="a43df-127">Luminance table</span></span><br /><br /> <span data-ttu-id="a43df-128">Таблица чроминанце</span><span class="sxs-lookup"><span data-stu-id="a43df-128">Chrominance table</span></span>|

## <a name="value"></a><span data-ttu-id="a43df-129">значения</span><span class="sxs-lookup"><span data-stu-id="a43df-129">Value</span></span>

<span data-ttu-id="a43df-130">Массив значений.</span><span class="sxs-lookup"><span data-stu-id="a43df-130">An array of values.</span></span> <span data-ttu-id="a43df-131">Формат значений определяется свойством <xref:System.Drawing.Imaging.PropertyItem.Type%2A>.</span><span class="sxs-lookup"><span data-stu-id="a43df-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>

## <a name="len"></a><span data-ttu-id="a43df-132">Len</span><span class="sxs-lookup"><span data-stu-id="a43df-132">Len</span></span>

<span data-ttu-id="a43df-133">Длина (в байтах) массива значений, на который указывает свойство <xref:System.Drawing.Imaging.PropertyItem.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="a43df-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>

## <a name="type"></a><span data-ttu-id="a43df-134">Type</span><span class="sxs-lookup"><span data-stu-id="a43df-134">Type</span></span>

<span data-ttu-id="a43df-135">Тип данных значений в массиве, на который указывает свойство `Value`.</span><span class="sxs-lookup"><span data-stu-id="a43df-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="a43df-136">В следующей таблице показаны форматы, указанные в значениях свойств `Type`.</span><span class="sxs-lookup"><span data-stu-id="a43df-136">The formats indicated by the `Type` property values are shown in the following table:</span></span>

|<span data-ttu-id="a43df-137">Числовое значение</span><span class="sxs-lookup"><span data-stu-id="a43df-137">Numeric value</span></span>|<span data-ttu-id="a43df-138">Описание</span><span class="sxs-lookup"><span data-stu-id="a43df-138">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="a43df-139">1</span><span class="sxs-lookup"><span data-stu-id="a43df-139">1</span></span>|<span data-ttu-id="a43df-140">`Byte`</span><span class="sxs-lookup"><span data-stu-id="a43df-140">A `Byte`</span></span>|
|<span data-ttu-id="a43df-141">2</span><span class="sxs-lookup"><span data-stu-id="a43df-141">2</span></span>|<span data-ttu-id="a43df-142">Массив объектов `Byte` в кодировке ASCII</span><span class="sxs-lookup"><span data-stu-id="a43df-142">An array of `Byte` objects encoded as ASCII</span></span>|
|<span data-ttu-id="a43df-143">3</span><span class="sxs-lookup"><span data-stu-id="a43df-143">3</span></span>|<span data-ttu-id="a43df-144">16-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="a43df-144">A 16-bit integer</span></span>|
|<span data-ttu-id="a43df-145">4</span><span class="sxs-lookup"><span data-stu-id="a43df-145">4</span></span>|<span data-ttu-id="a43df-146">32-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="a43df-146">A 32-bit integer</span></span>|
|<span data-ttu-id="a43df-147">5</span><span class="sxs-lookup"><span data-stu-id="a43df-147">5</span></span>|<span data-ttu-id="a43df-148">Массив из двух `Byte` объектов, представляющих рациональное число</span><span class="sxs-lookup"><span data-stu-id="a43df-148">An array of two `Byte` objects that represent a rational number</span></span>|
|<span data-ttu-id="a43df-149">6</span><span class="sxs-lookup"><span data-stu-id="a43df-149">6</span></span>|<span data-ttu-id="a43df-150">Не используется</span><span class="sxs-lookup"><span data-stu-id="a43df-150">Not used</span></span>|
|<span data-ttu-id="a43df-151">7</span><span class="sxs-lookup"><span data-stu-id="a43df-151">7</span></span>|<span data-ttu-id="a43df-152">Не определено</span><span class="sxs-lookup"><span data-stu-id="a43df-152">Undefined</span></span>|
|<span data-ttu-id="a43df-153">8</span><span class="sxs-lookup"><span data-stu-id="a43df-153">8</span></span>|<span data-ttu-id="a43df-154">Не используется</span><span class="sxs-lookup"><span data-stu-id="a43df-154">Not used</span></span>|
|<span data-ttu-id="a43df-155">9</span><span class="sxs-lookup"><span data-stu-id="a43df-155">9</span></span>|`SLong`|
|<span data-ttu-id="a43df-156">10</span><span class="sxs-lookup"><span data-stu-id="a43df-156">10</span></span>|`SRational`|

## <a name="example"></a><span data-ttu-id="a43df-157">Пример</span><span class="sxs-lookup"><span data-stu-id="a43df-157">Example</span></span>
  
<span data-ttu-id="a43df-158">Следующий пример кода считывает и отображает семь элементов метаданных в файле `FakePhoto.jpg`.</span><span class="sxs-lookup"><span data-stu-id="a43df-158">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="a43df-159">Второй элемент свойства (index 1) в списке имеет <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (производитель оборудования) и <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (массив байтов в кодировке ASCII).</span><span class="sxs-lookup"><span data-stu-id="a43df-159">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="a43df-160">В примере кода отображается значение этого элемента свойства.</span><span class="sxs-lookup"><span data-stu-id="a43df-160">The code example displays the value of that property item.</span></span>

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

<span data-ttu-id="a43df-161">Код выводит примерно следующий результат:</span><span class="sxs-lookup"><span data-stu-id="a43df-161">The code produces output similar to the following:</span></span>

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

## <a name="compiling-the-code"></a><span data-ttu-id="a43df-162">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a43df-162">Compiling the Code</span></span>

<span data-ttu-id="a43df-163">Предыдущий пример предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="a43df-163">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="a43df-164">Обработайте событие <xref:System.Windows.Forms.Control.Paint> формы и вставьте этот код в обработчик событий Paint.</span><span class="sxs-lookup"><span data-stu-id="a43df-164">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="a43df-165">Необходимо заменить `FakePhoto.jpg` именем образа и путем, допустимым в системе, и импортировать пространство имен `System.Drawing.Imaging`.</span><span class="sxs-lookup"><span data-stu-id="a43df-165">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="a43df-166">См. также</span><span class="sxs-lookup"><span data-stu-id="a43df-166">See also</span></span>

- [<span data-ttu-id="a43df-167">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="a43df-167">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="a43df-168">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="a43df-168">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
