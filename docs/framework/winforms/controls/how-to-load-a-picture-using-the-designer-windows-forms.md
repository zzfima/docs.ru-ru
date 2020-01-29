---
title: Практическое руководство. Загрузка изображения с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 12b90d561a18fcffaafb9c45b7fa6be6dd060215
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736327"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form)

С помощью элемента управления Windows Forms <xref:System.Windows.Forms.PictureBox> можно загружать и отображать изображение в форме во время разработки, присвоив свойству <xref:System.Windows.Forms.PictureBox.Image%2A> допустимое изображение. В следующей таблице приведены допустимые типы файлов.

|Тип|Расширение имени файла|
|---|---|
|Bitmap|BMP|
|Значок|ICO|
|GIF|GIF|
|Метафайл|. WMF|
|JPEG|JPG|

## <a name="to-display-a-picture-at-design-time"></a>Отображение рисунка во время разработки

1. Нарисуйте элемент управления <xref:System.Windows.Forms.PictureBox> в форме.

2. В окне **Свойства** выберите свойство <xref:System.Windows.Forms.PictureBox.Image%2A>, а затем нажмите кнопку с многоточием, чтобы открыть диалоговое окно **Открытие** .

3. Если вы ищете конкретный тип файла (например, GIF-файлы), выберите его в поле **файлы типа** .

4. Выберите файл, который требуется отобразить.

## <a name="to-clear-the-picture-at-design-time"></a>Очистка рисунка во время разработки

1. В окне **Свойства** выберите свойство <xref:System.Windows.Forms.PictureBox.Image%2A>. Щелкните правой кнопкой мыши маленький эскиз изображения, который отображается слева от имени объекта Image, и выберите команду **сбросить**.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.PictureBox>
- [Общие сведения об элементе управления PictureBox](picturebox-control-overview-windows-forms.md)
- [Практическое руководство. Изменение размера или размещения изображения во время выполнения](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Практическое руководство. Установка изображений во время выполнения](how-to-set-pictures-at-run-time-windows-forms.md)
- [Элемент управления PictureBox](picturebox-control-windows-forms.md)
