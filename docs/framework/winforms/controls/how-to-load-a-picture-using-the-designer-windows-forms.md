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
ms.openlocfilehash: 1d95d5baafa42c7dea40933ba837b684d90b7b2b
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972375"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Практическое руководство. Загрузка изображения с помощью конструктора (Windows Forms)

С помощью элемента <xref:System.Windows.Forms.PictureBox> управления Windows Forms можно загружать и отображать изображение в форме во время разработки, <xref:System.Windows.Forms.PictureBox.Image%2A> присвоив свойству допустимое изображение. В следующей таблице приведены допустимые типы файлов.

|Тип|Расширение имени файла|
|----------|-------------------------|
|Bitmap|. bmp|
|Значок|ICO|
|GIF|GIF|
|Метафайл|. WMF|
|JPEG|JPG|

> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).

## <a name="to-display-a-picture-at-design-time"></a>Отображение рисунка во время разработки

1. <xref:System.Windows.Forms.PictureBox> Рисование элемента управления в форме.

2. На окно свойств выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство, а затем нажмите кнопку с многоточием, чтобы открыть диалоговое окно **Открытие** .

3. Если вы ищете конкретный тип файла (например, GIF-файлы), выберите его в поле **файлы типа** .

4. Выберите файл, который требуется отобразить.

## <a name="to-clear-the-picture-at-design-time"></a>Очистка рисунка во время разработки

1. В окне **Свойства** выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство и щелкните правой кнопкой мыши маленький эскиз изображения, который отображается слева от имени объекта изображения. Нажмите кнопку **сбросить**.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.PictureBox>
- [Общие сведения об элементе управления PictureBox](picturebox-control-overview-windows-forms.md)
- [Практическое руководство. Изменение размера или расположения изображения во время выполнения](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Практическое руководство. Задание изображений во время выполнения](how-to-set-pictures-at-run-time-windows-forms.md)
- [Элемент управления PictureBox](picturebox-control-windows-forms.md)
