---
title: "Практическое руководство. Создание эскизов изображений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b8eeb856fabd895e171c0ad8739ae6a63b5c7065
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-thumbnail-images"></a>Практическое руководство. Создание эскизов изображений
Эскиз — это уменьшенная изображения. Можно создать эскиз путем вызова <xref:System.Drawing.Image.GetThumbnailImage%2A> метод <xref:System.Drawing.Image> объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Drawing.Image> объекта из JPG-файла. Исходное изображение имеет ширину 640 пикселей и высотой 479 пикселей. Код создает эскиз изображения, имеет ширину 100 пикселей и высотой 100 пикселей.  
  
 На следующем рисунке эскиз.  
  
 ![Эскиз](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  В этом примере метод обратного вызова объявлен, но никогда не используется. Это поддерживается всеми версиями GDI +.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>. Чтобы запустить пример, выполните следующие действия.  
  
1.  Создайте новое приложение Windows Forms.  
  
2.  Добавьте в форму в примере кода.  
  
3.  Создание обработчика для формы <xref:System.Windows.Forms.Control.Paint> событий  
  
4.  В <xref:System.Windows.Forms.Control.Paint> обработчик, вызовите `GetThumbnail` метод и передайте `e` для <xref:System.Windows.Forms.PaintEventArgs>.  
  
5.  Найдите файл образа, который вы хотите создать эскиз.  
  
6.  В `GetThumbnail` метода, укажите путь и имя файла для изображения.  
  
7.  Нажмите клавишу F5 для запуска примера.  
  
     В форме появится эскиз 100 на 100.  
  
## <a name="see-also"></a>См. также  
 [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Работа с растровыми и векторными изображениями, значками и метафайлами](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
