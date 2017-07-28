---
title: "Практическое руководство. Создание эскизов изображений | Microsoft Docs"
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
  - "изображения [Windows Forms], создание эскизов рисунков"
  - "эскизы рисунков, создание"
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Практическое руководство. Создание эскизов изображений
Эскиз изображения — это сильно уменьшенный вариант изображения.  Чтобы создать эскиз изображения, следует вызвать метод <xref:System.Drawing.Image.GetThumbnailImage%2A> объекта <xref:System.Drawing.Image>.  
  
## Пример  
 В следующем примере показано создание объекта <xref:System.Drawing.Image> из JPG\-файла.  Исходное изображение имеет ширину 640 пикселей и высоту 479 пикселей.  Приведенный ниже код создает эскиз изображения, имеющий ширину 100 пикселей и высоту 100 пикселей.  
  
 Эскиз изображения показан на следующем рисунке.  
  
 ![Эскиз рисунка](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  В этом пример объявляется метод обратного вызова, но он не используется.  Это поддерживается всеми версиями GDI\+.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  Чтобы выполнить пример, выполните следующие действия.  
  
1.  Создание нового приложения Windows Forms.  
  
2.  Добавьте код примера в форму.  
  
3.  Создайте обработчик событий для события формы <xref:System.Windows.Forms.Control.Paint>.  
  
4.  В обработчике событий <xref:System.Windows.Forms.Control.Paint> вызовите метод `GetThumbnail` и передайте параметр `e` для <xref:System.Windows.Forms.PaintEventArgs>.  
  
5.  Найдите файл изображения для которого нужно создать эскиз.  
  
6.  В методе `GetThumbnail` укажите путь и имя файла изображения.  
  
7.  Нажмите клавишу F5 для запуска примера.  
  
     В форме появится эскиз изображения размером 100х100.  
  
## См. также  
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Работа с растровыми и векторными изображениями](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)