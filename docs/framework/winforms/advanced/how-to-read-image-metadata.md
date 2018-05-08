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
ms.openlocfilehash: 92ce4eb8d51fbd25f9a129a629dc47bfb9941f34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-image-metadata"></a>Практическое руководство. Чтение метаданных изображения
Некоторые файлы изображений содержат метаданные, которые могут прочитать, чтобы определить возможности изображения. Например цифровая фотография может содержать метаданные, которые могут прочитать, чтобы определить Марка и модель камеры, использованной для создания образа. С [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], можно считывать существующие метаданные и файлы изображений, также могут записывать новые метаданные.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] хранит каждый отдельный блок метаданных в <xref:System.Drawing.Imaging.PropertyItem> объекта. Можно прочитать <xref:System.Drawing.Image.PropertyItems%2A> свойство <xref:System.Drawing.Image> объекта для извлечения метаданных из файла. <xref:System.Drawing.Image.PropertyItems%2A> Свойство возвращает массив <xref:System.Drawing.Imaging.PropertyItem> объектов.  
  
 Объект <xref:System.Drawing.Imaging.PropertyItem> имеет следующие четыре свойства: `Id`, `Value`, `Len`, и `Type`.  
  
## <a name="id"></a>Id  
 Тег, определяющий элемент метаданных. Некоторые значения, которые могут быть назначены <xref:System.Drawing.Imaging.PropertyItem.Id%2A> показано в следующей таблице.  
  
|Шестнадцатеричное значение|Описание|  
|-----------------------|-----------------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Изображение заголовка<br /><br /> Изготовитель оборудования<br /><br /> Модель оборудования<br /><br /> ExifDTOriginal<br /><br /> Время выдержки EXIF<br /><br /> Таблица яркости<br /><br /> Таблица цветности|  
  
## <a name="value"></a>Значение  
 Массив значений. Формат значений определяется <xref:System.Drawing.Imaging.PropertyItem.Type%2A> свойство.  
  
## <a name="len"></a>Len  
 Размер (в байтах) массива значений, на который указывает <xref:System.Drawing.Imaging.PropertyItem.Value%2A> свойство.  
  
## <a name="type"></a>Тип  
 Тип данных значения в массиве, на который указывает `Value` свойство. Типы, определяемые по `Type` в следующей таблице показаны значения свойств  
  
|Числовое значение|Описание|  
|-------------------|-----------------|  
|1|`Byte`|  
|2|Массив `Byte` объекты в кодировке ASCII|  
|3|16-разрядное целое число|  
|4|32-разрядное целое число|  
|5|Массив из двух `Byte` объектов, представляющих рациональное число|  
|6|Не используется|  
|7|Не определено|  
|8|Не используется|  
|9|`SLong`|  
|10|`SRational`|  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере кода считывает и отображает семи блоков метаданных из файла `FakePhoto.jpg`. Второй элемент свойства (позиция 1) в списке имеет <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (производитель оборудования) и <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (массив байтов в кодировке ASCII). Пример кода отображает значение данного свойства.  
  
 Код создает выходные данные, аналогичные следующим:  
  
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
  
### <a name="code"></a>Код  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>. Обрабатывать формы <xref:System.Windows.Forms.Control.Paint> событий и вставьте этот код в обработчик событий paint. Необходимо заменить `FakePhoto.jpg` допустимы для системы и импорта путь и имя образа `System.Drawing.Imaging` пространства имен.  
  
## <a name="see-also"></a>См. также  
 [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Работа с растровыми и векторными изображениями, значками и метафайлами](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
