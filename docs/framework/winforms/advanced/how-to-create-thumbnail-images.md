---
title: Как выполнить Создание эскизов изображений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: fd5e0b5341a712f25f9d41670f9b3ede5414dda4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497046"
---
# <a name="how-to-create-thumbnail-images"></a>Как выполнить Создание эскизов изображений
Эскиз — это компактная версия образа. Можно создать изображение эскиза путем вызова <xref:System.Drawing.Image.GetThumbnailImage%2A> метод <xref:System.Drawing.Image> объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Drawing.Image> объект из JPG-файла. Исходное изображение имеет 640 пикселей в ширину и высоту 479 пикселей. Код создает эскиз с 100 пикселей в ширину и высоту 100 пикселей.  
  
 На следующем рисунке эскиз.  
  
 ![Эскиз](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  В этом примере метод обратного вызова является объявлен, но никогда не используется. Это поддерживается всеми версиями GDI +.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>. Чтобы запустить пример, выполните следующие действия.  
  
1.  Создайте новое приложение Windows Forms.  
  
2.  В примере кода добавьте в форму.  
  
3.  Создайте обработчик для формы <xref:System.Windows.Forms.Control.Paint> событий  
  
4.  В <xref:System.Windows.Forms.Control.Paint> обработчик, вызов `GetThumbnail` метод и передать `e` для <xref:System.Windows.Forms.PaintEventArgs>.  
  
5.  Найдите файл изображения, который требуется создать эскиз.  
  
6.  В `GetThumbnail` метод, укажите путь и имя файла для изображения.  
  
7.  Нажмите клавишу F5 для запуска примера.  
  
     В форме появится эскиз 100 на 100.  
  
## <a name="see-also"></a>См. также
- [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
- [Работа с растровыми и векторными изображениями, значками и метафайлами](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
