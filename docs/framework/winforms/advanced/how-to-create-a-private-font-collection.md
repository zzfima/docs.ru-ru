---
title: Практическое руководство. Создание частной коллекции шрифтов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: 824d42c40b07e8662395e7a1286b9a5a6112c415
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-private-font-collection"></a>Практическое руководство. Создание частной коллекции шрифтов
<xref:System.Drawing.Text.PrivateFontCollection> Класс наследует от <xref:System.Drawing.Text.FontCollection> абстрактного базового класса. Можно использовать <xref:System.Drawing.Text.PrivateFontCollection> объекта для сохранения набора шрифтов, предназначенных для конкретного приложения. Частной коллекции может включать шрифты установленной системы, а также шрифты, которые не были установлены на компьютере. Чтобы добавить файл шрифта частной коллекции, вызовите <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> метод <xref:System.Drawing.Text.PrivateFontCollection> объекта.  
  
 <xref:System.Drawing.Text.FontCollection.Families%2A> Свойство <xref:System.Drawing.Text.PrivateFontCollection> объект содержит массив <xref:System.Drawing.FontFamily> объектов.  
  
 Количество семейств шрифтов в частной коллекции не обязательно совпадает с количеством файлов шрифтов, которые были добавлены в коллекцию. Например предположим, что файлы ArialBd.tff, Times.tff и TimesBd.tff добавить в коллекцию. Будет существовать три файла, но только два семейства в коллекции, так как Times.tff и TimesBd.tff относятся к одному семейству.  
  
## <a name="example"></a>Пример  
 В следующем примере добавляется по следующим файлам три шрифта <xref:System.Drawing.Text.PrivateFontCollection> объекта:  
  
-   C:\\*systemroot*\Fonts\Arial.tff (Arial, обычный)  
  
-   C:\\*systemroot*\Fonts\CourBI.tff (Courier New, полужирный курсив)  
  
-   C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, полужирный)  
  
 Этот код извлекает массив <xref:System.Drawing.FontFamily> объектов из <xref:System.Drawing.Text.FontCollection.Families%2A> свойство <xref:System.Drawing.Text.PrivateFontCollection> объекта.  
  
 Для каждого <xref:System.Drawing.FontFamily> объекта в коллекции, этот код вызывает <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> метод, чтобы определить, будут ли доступны различные стили (обычный, полужирный, курсив, полужирный курсив, подчеркнутый и зачеркнутый). Аргументы, передаваемые <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> метод являются членами <xref:System.Drawing.FontStyle> перечисления.  
  
 Если сочетание заданного семейства и стиля, <xref:System.Drawing.Font> объект создается с помощью этого семейства и стиля. Первый аргумент, переданный <xref:System.Drawing.Font.%23ctor%2A> конструктор является имя семейства шрифтов (не <xref:System.Drawing.FontFamily> объекта, как в случае других вариантах <xref:System.Drawing.Font.%23ctor%2A> конструктора). После <xref:System.Drawing.Font> объект создан, он передается <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> класса для отображения имени семейства вместе с именем стиля.  
  
 Выходные данные приведенного ниже кода аналогична выходные данные, показанные на следующем рисунке.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")  
  
 Arial.tff (который добавлялся в частную коллекцию шрифтов в следующем примере кода) — это файл шрифта Arial обычного стиля. Обратите внимание, что выходные данные программы отображает доступные стили отличный от обычной для семейства шрифтов Arial. Причина этого заключается в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] может имитировать полужирный, курсив и полужирный курсив из обычного стиля. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] также можно создавать зачеркивание и подчеркивание обычного стиля.  
  
 Аналогичным образом [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] можно имитировать начертание полужирный курсив полужирный стиль или курсивное начертание. Выходные данные программы показывает, что начертание полужирный курсив доступно для семейства Times, хотя TimesBd.tff (Times New Roman, полужирный) является единственным файлом раз в коллекции.  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример кода предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
