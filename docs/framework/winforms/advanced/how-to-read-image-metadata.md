---
title: "Практическое руководство. Чтение метаданных изображения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "метаданные, элемент свойства"
  - "метаданные, чтение изображения"
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Чтение метаданных изображения
Некоторые файлы с изображениями содержат метаданные, которые можно прочитать, чтобы определить свойства изображения.  Например, цифровая фотография может содержать метаданные, которые позволяют определить модель камеры, с помощью которой была получена данная фотография.  С помощью интерфейса [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] можно считывать существующие метаданные, а также добавлять новые метаданные в файлы с изображениями.  
  
 Интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] хранит каждый отдельный блок метаданных в объекте <xref:System.Drawing.Imaging.PropertyItem>.  Чтобы получить все метаданные файла, можно прочитать свойство <xref:System.Drawing.Image.PropertyItems%2A> объекта <xref:System.Drawing.Image>.  Свойство <xref:System.Drawing.Image.PropertyItems%2A> возвращает массив объектов <xref:System.Drawing.Imaging.PropertyItem>.  
  
 Объект <xref:System.Drawing.Imaging.PropertyItem> имеет следующие четыре свойства: `Id`, `Value`, `Len` и `Type`.  
  
## Идентификатор  
 Тег, идентифицирующий блок метаданных.  Некоторые из значений, которые может принимать <xref:System.Drawing.Imaging.PropertyItem.Id%2A>, приводятся в следующей таблице.  
  
|Шестнадцатеричное значение|Описание|  
|--------------------------------|--------------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|Название изображения<br /><br /> Производитель оборудования<br /><br /> Модель оборудования<br /><br /> ExifDTOriginal<br /><br /> Exif — время выдержки<br /><br /> Таблица светимости<br /><br /> Таблица хроматических данных|  
  
## Значение  
 Массив значений.  Формат значений определяется свойством <xref:System.Drawing.Imaging.PropertyItem.Type%2A>.  
  
## Len  
 Размер \(в байтах\) массива значений, на который указывает свойство <xref:System.Drawing.Imaging.PropertyItem.Value%2A>.  
  
## Тип  
 Тип элементов массива, на который указывает свойство `Value`.  Типы, определяемые по значению свойства `Type`, приводятся в следующей таблице.  
  
|Числовое значение|Описание|  
|-----------------------|--------------|  
|1|Элемент `Byte`|  
|2|Массив объектов `Byte` в кодировке ASCII|  
|3|16\-разрядное целое число|  
|4|32\-разрядное целое число|  
|5|Массив из двух объектов `Byte`, представляющих рациональное число|  
|6|Не используется|  
|7|Не определено|  
|8|Не используется|  
|9|`SLong`|  
|10|`SRational`|  
  
## Пример  
  
### Описание  
 В следующем примере кода осуществляется считывание и отображение семи блоков метаданных из файла `FakePhoto.jpg`.  Второе свойство в списке \(индекс 1\) имеет значение <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F \(производитель оборудование\) и <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 \(массив объектов byte в кодировке ASCII\).  В примере кода отображается значение данного свойства.  
  
 Результат выполнения этого кода будет выглядеть примерно следующим образом:  
  
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
  
### Код  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  Обработайте событие <xref:System.Windows.Forms.Control.Paint> формы и вставьте этот код в обработчик событий paint.  Имя изображения `FakePhoto.jpg` должно быть заменено на имя изображения и путь в вашей системе, и пространство имен `System.Drawing.Imaging` должно быть импортировано.  
  
## См. также  
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Работа с растровыми и векторными изображениями](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)