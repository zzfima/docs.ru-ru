---
title: "Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "формы, отображение изображений"
  - "изображения [Windows Forms], отображение в формах Windows Forms"
  - "форматы рисунков"
  - "PictureBox - элемент управления [Windows Forms], добавление рисунков"
  - "рисунки, отображение"
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form)
С помощью элемента управления Windows Forms <xref:System.Windows.Forms.PictureBox> можно загружать и отображать рисунок на форме в режиме разработки путем задания свойству <xref:System.Windows.Forms.PictureBox.Image%2A> значения допустимого рисунка.  В следующей таблице представлены допустимые типы файлов.  
  
|Тип|Расширение имени файла|  
|---------|----------------------------|  
|Растровое изображение|BMP|  
|Значок|ICO|  
|GIF|GIF|  
|Метафайл|WMF|  
|JPEG|JPG|  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы отобразить рисунок в режиме разработки  
  
1.  Нарисуйте элемент управления <xref:System.Windows.Forms.PictureBox> в форме.  
  
2.  В окне "Свойства" выберите свойство <xref:System.Windows.Forms.PictureBox.Image%2A>, затем нажмите кнопку с многоточием для отображения диалогового окна **Открыть**.  
  
3.  Если требуется файл определенного типа \(например, с расширением .GIF\), можно выбрать категорию в поле **Тип файлов**.  
  
4.  Выберите файл для отображения.  
  
### Чтобы очистить рисунок в режиме разработки  
  
1.  В диалоговом окне **Свойства** выберите свойство <xref:System.Windows.Forms.PictureBox.Image%2A> и щелкните правой кнопкой мыши маленький эскиз рисунка, который появляется слева от имени объекта рисунка.  Выберите **Сброс**.  
  
## См. также  
 <xref:System.Windows.Forms.PictureBox>   
 [Общие сведения об элементе управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)   
 [Практическое руководство. Изменение размера или размещения изображения во время выполнения](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)   
 [Практическое руководство. Установка изображений во время выполнения](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)   
 [Элемент управления PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)