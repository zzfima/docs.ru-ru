---
title: Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form)
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: e01e5d1dc0fad8171e705e85debc2b15d6a506eb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466538"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form)
С помощью Windows Forms <xref:System.Windows.Forms.PictureBox> элемента управления, можно загружать и отображать изображение в форме во время разработки, установив <xref:System.Windows.Forms.PictureBox.Image%2A> свойство допустимого рисунка. В следующей таблице показаны допустимые типы файлов.  
  
|Тип|Расширение имени файла|  
|----------|-------------------------|  
|Bitmap|.bmp|  
|Значок|ICO|  
|GIF|GIF|  
|Метафайл|.wmf|  
|JPEG|.jpg|  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-display-a-picture-at-design-time"></a>Для отображения рисунка во время разработки  
  
1.  Рисование <xref:System.Windows.Forms.PictureBox> управления на форме.  
  
2.  В окне «Свойства» выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойства, а затем нажмите кнопку с многоточием для отображения **откройте** диалоговое окно.  
  
3.  Если вы ищете файлов определенного типа (например, GIF-файлы), выберите ее в **файлы типа** поле.  
  
4.  Выберите файл, который вы хотите отобразить.  
  
### <a name="to-clear-the-picture-at-design-time"></a>Чтобы очистить рисунок во время разработки  
  
1.  На **свойства** выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство и щелкните правой кнопкой мыши небольшой эскиза, который отображается слева от имени объекта образа. Выберите **сбросить**.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.PictureBox>  
 [Общие сведения об элементе управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [Практическое руководство. Изменение размера или размещения изображения во время выполнения](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [Практическое руководство. Установка изображений во время выполнения](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [Элемент управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
