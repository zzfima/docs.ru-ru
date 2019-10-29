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
# <a name="how-to-read-image-metadata"></a>Практическое руководство. Чтение метаданных изображения

Некоторые файлы изображений содержат метаданные, которые можно прочитать, чтобы определить характеристики изображения. Например, цифровая фотография может содержать метаданные, которые можно прочитать для определения марки и модели камеры, используемой для записи образа. С помощью GDI+ можно считывать существующие метаданные, а также записывать новые метаданные в файлы изображений.

GDI+ сохраняет отдельный фрагмент метаданных в объекте <xref:System.Drawing.Imaging.PropertyItem>. Можно прочитать свойство <xref:System.Drawing.Image.PropertyItems%2A> объекта <xref:System.Drawing.Image>, чтобы получить все метаданные из файла. Свойство <xref:System.Drawing.Image.PropertyItems%2A> возвращает массив объектов <xref:System.Drawing.Imaging.PropertyItem>.

Объект <xref:System.Drawing.Imaging.PropertyItem> имеет следующие четыре свойства: `Id`, `Value`, `Len`и `Type`.

## <a name="id"></a>Идентификатор

Тег, определяющий элемент метаданных. Некоторые значения, которые могут быть назначены <xref:System.Drawing.Imaging.PropertyItem.Id%2A>, показаны в следующей таблице.

|Шестнадцатеричное значение|Описание|
|-----------------------|-----------------|
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Название образа<br /><br /> Производитель оборудования<br /><br /> Модель оборудования<br /><br /> ексифдторигинал<br /><br /> Время экспозиции EXIF<br /><br /> Таблица освещенности<br /><br /> Таблица чроминанце|

## <a name="value"></a>значения

Массив значений. Формат значений определяется свойством <xref:System.Drawing.Imaging.PropertyItem.Type%2A>.

## <a name="len"></a>Len

Длина (в байтах) массива значений, на который указывает свойство <xref:System.Drawing.Imaging.PropertyItem.Value%2A>.

## <a name="type"></a>Type

Тип данных значений в массиве, на который указывает свойство `Value`. В следующей таблице показаны форматы, указанные в значениях свойств `Type`.

|Числовое значение|Описание|
|-------------------|-----------------|
|1|`Byte`|
|2|Массив объектов `Byte` в кодировке ASCII|
|3|16-разрядное целое число|
|4|32-разрядное целое число|
|5|Массив из двух `Byte` объектов, представляющих рациональное число|
|6|Не используется|
|7|Не определено|
|8|Не используется|
|9|`SLong`|
|10|`SRational`|

## <a name="example"></a>Пример
  
Следующий пример кода считывает и отображает семь элементов метаданных в файле `FakePhoto.jpg`. Второй элемент свойства (index 1) в списке имеет <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (производитель оборудования) и <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (массив байтов в кодировке ASCII). В примере кода отображается значение этого элемента свойства.

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

Код выводит примерно следующий результат:

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

Предыдущий пример предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика событий <xref:System.Windows.Forms.Control.Paint>. Обработайте событие <xref:System.Windows.Forms.Control.Paint> формы и вставьте этот код в обработчик событий Paint. Необходимо заменить `FakePhoto.jpg` именем образа и путем, допустимым в системе, и импортировать пространство имен `System.Drawing.Imaging`.

## <a name="see-also"></a>См. также

- [Изображения, точечные рисунки и метафайлы](images-bitmaps-and-metafiles.md)
- [Работа с растровыми и векторными изображениями, значками и метафайлами](working-with-images-bitmaps-icons-and-metafiles.md)
