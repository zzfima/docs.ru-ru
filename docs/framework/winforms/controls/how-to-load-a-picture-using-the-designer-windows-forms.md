---
title: "Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9049bf5f9467401bff098459b8f5ed55c1ee1975
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form)
С помощью Windows Forms <xref:System.Windows.Forms.PictureBox> управления, можно загружать и отображать рисунок на форме во время разработки, задав <xref:System.Windows.Forms.PictureBox.Image%2A> свойство допустимого рисунка. В следующей таблице показаны допустимые типы файлов.  
  
|Тип|Расширение имени файла|  
|----------|-------------------------|  
|Bitmap|.bmp|  
|Значок|ICO|  
|GIF|GIF|  
|Метафайл|.wmf|  
|JPEG|.jpg|  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-display-a-picture-at-design-time"></a>Для отображения рисунка во время разработки  
  
1.  Рисование <xref:System.Windows.Forms.PictureBox> элемента управления в форме.  
  
2.  В окне «Свойства» выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойства, а затем нажмите кнопку с многоточием для отображения **откройте** диалоговое окно.  
  
3.  Если вы ищете файлов определенного типа (например, GIF-файлы), выберите ее в **файлы типа** поле.  
  
4.  Выберите файл, который требуется отобразить.  
  
### <a name="to-clear-the-picture-at-design-time"></a>Чтобы очистить рисунок во время разработки  
  
1.  На **свойства** выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство и щелкните правой кнопкой мыши отображается слева от имени объекта рисунка небольшой эскиз. Выберите **Сброс**.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.PictureBox>  
 [Общие сведения об элементе управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [Практическое руководство. Изменение размера или размещения изображения во время выполнения](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [Практическое руководство. Установка изображений во время выполнения](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [Элемент управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
