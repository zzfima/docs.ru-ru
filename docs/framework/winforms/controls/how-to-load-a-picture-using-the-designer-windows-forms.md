---
title: Практическое руководство. Загрузка изображения с помощью конструктора (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 818bc63b5b3bea6c73804f716a72ba3cd1a62b4c
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039683"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Практическое руководство. Загрузка изображения с помощью конструктора (Windows Forms)

С помощью элемента <xref:System.Windows.Forms.PictureBox> управления Windows Forms можно загружать и отображать изображение в форме во время разработки, <xref:System.Windows.Forms.PictureBox.Image%2A> присвоив свойству допустимое изображение. В следующей таблице приведены допустимые типы файлов.

|Тип|Расширение имени файла|
|---|---|
|Bitmap|. bmp|
|Значок|ICO|
|GIF|GIF|
|Метафайл|. WMF|
|JPEG|JPG|

## <a name="to-display-a-picture-at-design-time"></a>Отображение рисунка во время разработки

1. <xref:System.Windows.Forms.PictureBox> Рисование элемента управления в форме.

2. В окне **Свойства** выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство, а затем нажмите кнопку с многоточием, чтобы открыть диалоговое окно **Открытие** .

3. Если вы ищете конкретный тип файла (например, GIF-файлы), выберите его в поле **файлы типа** .

4. Выберите файл, который требуется отобразить.

## <a name="to-clear-the-picture-at-design-time"></a>Очистка рисунка во время разработки

1. В окне **Свойства** выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство. Щелкните правой кнопкой мыши маленький эскиз изображения, который отображается слева от имени объекта Image, и выберите команду **сбросить**.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.PictureBox>
- [Общие сведения об элементе управления PictureBox](picturebox-control-overview-windows-forms.md)
- [Практическое руководство. Изменение размера или расположения изображения во время выполнения](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Практическое руководство. Задание изображений во время выполнения](how-to-set-pictures-at-run-time-windows-forms.md)
- [Элемент управления PictureBox](picturebox-control-windows-forms.md)
