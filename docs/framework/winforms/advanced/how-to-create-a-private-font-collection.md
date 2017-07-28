---
title: "Практическое руководство. Создание частной коллекции шрифтов | Microsoft Docs"
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
  - "шрифты, создание частных коллекций"
  - "частные коллекции шрифтов, создание"
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Создание частной коллекции шрифтов
Класс <xref:System.Drawing.Text.PrivateFontCollection> наследуется от абстрактного базового класса <xref:System.Drawing.Text.FontCollection>.  Объект <xref:System.Drawing.Text.PrivateFontCollection> можно использовать для хранения некоторого набора шрифтов, предназначенных для конкретного приложения.  Частная коллекция шрифтов может включать как установленные системные шрифты, так и шрифты, которые не установлены на компьютере.  Чтобы добавить файл со шрифтом в частную коллекцию шрифтов, следует вызвать метод <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> объекта <xref:System.Drawing.Text.PrivateFontCollection>.  
  
 Свойство <xref:System.Drawing.Text.FontCollection.Families%2A> объекта <xref:System.Drawing.Text.PrivateFontCollection> содержит массив объектов <xref:System.Drawing.FontFamily>.  
  
 Количество семейств шрифтов в частной коллекции не обязательно совпадает с количеством файлов со шрифтами, которые были добавлены в эту коллекцию.  Например, предположим, что в коллекцию добавляются файлы ArialBd.tff, Times.tff и TimesBd.tff.  В коллекции в этом случае будут содержаться три файла, но только два семейства шрифтов, потому что Times.tff и TimesBd.tff относятся к одному семейству.  
  
## Пример  
 В следующем примере в объект <xref:System.Drawing.Text.PrivateFontCollection> добавляются следующие три файла со шрифтами:  
  
-   C:\\*systemroot*\\Fonts\\Arial.tff \(Arial, обычный\)  
  
-   C:\\*systemroot*\\Fonts\\CourBI.tff \(Courier New, полужирный курсив\)  
  
-   C:\\*systemroot*\\Fonts\\TimesBd.tff \(Times New Roman, полужирный\)  
  
 Этот код извлекает массив объектов <xref:System.Drawing.FontFamily> из свойства <xref:System.Drawing.Text.FontCollection.Families%2A> объекта <xref:System.Drawing.Text.PrivateFontCollection>.  
  
 Для каждого объекта <xref:System.Drawing.FontFamily> из этой коллекции код вызывает метод <xref:System.Drawing.FontFamily.IsStyleAvailable%2A>, чтобы определить, доступны ли различные начертания \(обычный, полужирный, курсив, полужирный курсив, подчеркивание и зачеркивание\).  Параметры, передаваемые методу <xref:System.Drawing.FontFamily.IsStyleAvailable%2A>, являются членами перечисления <xref:System.Drawing.FontStyle>.  
  
 Если рассматриваемое сочетание "семейство — начертание" доступно, то на основе этого сочетания семейства и начертания создается объект <xref:System.Drawing.Font>.  Первым параметром, передаваемым конструктору <xref:System.Drawing.Font.%23ctor%2A>, является название семейства шрифтов \(а не объект <xref:System.Drawing.FontFamily>, как в других вариантах конструктора <xref:System.Drawing.Font.%23ctor%2A>\).  После создания объект <xref:System.Drawing.Font> передается методу <xref:System.Drawing.Graphics.DrawString%2A> класса <xref:System.Drawing.Graphics> для отображения названия семейства вместе с названием начертания.  
  
 Результат работы приведенного ниже кода выглядит примерно следующим образом.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")  
  
 Arial.tff \(который добавлялся в частную коллекцию шрифтов в следующем примере\) является файлом шрифта Arial обычного начертания.  Обратите, однако, внимание, что в списке, выводимом программой, присутствуют несколько доступных начертаний для семейства шрифтов Arial, а не только обычное начертание.  Это связано с тем, что интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] может имитировать такие начертания, как полужирный, курсив и полужирный курсив, на основе обычного начертания.  Кроме того, с помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] можно создавать зачеркивание и подчеркивание обычного начертания.  
  
 Похожим образом интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] может имитировать начертание полужирный курсив на основе либо полужирного начертания, либо курсива.  Список, выводимый программой, показывает, что начертание полужирный курсив доступно для семейства Times, хотя TimesBd.tff \(Times New Roman, полужирный\) является единственным файлом семейства шрифтов Times в коллекции.  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 <xref:System.Drawing.Text.PrivateFontCollection>   
 [Шрифты и текст](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)