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
# <a name="how-to-read-image-metadata"></a>Практическое руководство. Чтение метаданных изображения

Некоторые файлы изображений содержат метаданные, которые можно прочитать для определения особенностей изображения. Например, цифровая фотография может содержать метаданные, которые можно прочитать, чтобы определить модель камеры, используемой для захвата изображения. С помощью GDI можно читать существующие метаданные, а также писать новые метаданные в файлы изображений.

GDI хранит отдельный фрагмент метаданных <xref:System.Drawing.Imaging.PropertyItem> в объекте. Вы можете <xref:System.Drawing.Image.PropertyItems%2A> прочитать <xref:System.Drawing.Image> свойство объекта для извлечения всех метаданных из файла. Свойство <xref:System.Drawing.Image.PropertyItems%2A> возвращает массив <xref:System.Drawing.Imaging.PropertyItem> объектов.

Объект <xref:System.Drawing.Imaging.PropertyItem> имеет следующие четыре `Id` `Value`свойства: , , `Len`и `Type`.

## <a name="id"></a>Идентификатор

Тег, идентифицирующие элемент метаданных. Некоторые значения, которым можно <xref:System.Drawing.Imaging.PropertyItem.Id%2A> присвоить, отображаются в следующей таблице:

|Гексадецимальная ценность|Описание|
|-----------------------|-----------------|
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Название изображения<br /><br /> Производитель оборудования<br /><br /> Модель оборудования<br /><br /> ExifDTOriginal<br /><br /> Время экспозиции Exif<br /><br /> Таблица luminance<br /><br /> Хроминас стол|

## <a name="value"></a>Значение

Массив значений типа . Формат значений определяется <xref:System.Drawing.Imaging.PropertyItem.Type%2A> свойством.

## <a name="len"></a>Len

Длина (в байтах) массива значений, <xref:System.Drawing.Imaging.PropertyItem.Value%2A> на которые указывает свойство.

## <a name="type"></a>Тип

Тип данных значений в массиве, `Value` на который указывает свойство. Форматы, указанные `Type` значениями свойств, отображаются в следующей таблице:

|Числовое значение|Описание|
|-------------------|-----------------|
|1|`Byte`;|
|2|Массив объектов, кодированных `Byte` как ASCII|
|3|16-битный ряд|
|4|32-битный ряд|
|5|Массив из `Byte` двух объектов, представляющих рациональное число|
|6|Не используется|
|7|Не определено.|
|8|Не используется|
|9|`SLong`|
|10|`SRational`|

## <a name="example"></a>Пример
  
Следующий пример кода читает и отображает семь фрагментов `FakePhoto.jpg`метаданных в файле. Второй (индекс 1) элемент свойства <xref:System.Drawing.Imaging.PropertyItem.Id%2A> в списке имеет 0x010F (производитель оборудования) и <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-кодированный байт массив). Пример кода отображает значение этого элемента свойства.

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

Код производит выход, аналогичный следующим:

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

## <a name="compiling-the-code"></a>Компиляция кода

Предыдущий пример предназначен для использования с формами Windows, и он требует, <xref:System.Windows.Forms.PaintEventArgs> `e`который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий. Обвязайте <xref:System.Windows.Forms.Control.Paint> событие формы и вставьте этот код в обработчик события краски. Необходимо заменить `FakePhoto.jpg` имя изображения и траекторию, действительную в вашей системе, и импортировать пространство `System.Drawing.Imaging` имен.

## <a name="see-also"></a>См. также раздел

- [Изображения, Bitmaps и Метафайлы](images-bitmaps-and-metafiles.md)
- [Работа с растровыми и векторными изображениями](working-with-images-bitmaps-icons-and-metafiles.md)
