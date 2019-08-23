---
title: Практическое руководство. Создание эскизов изображений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 786a92d99f5e7a0c27f502efa9a5fe617ac4d4d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923760"
---
# <a name="how-to-create-thumbnail-images"></a>Практическое руководство. Создание эскизов изображений
Эскиз изображения — это небольшая версия изображения. Можно создать эскиз изображения, вызвав <xref:System.Drawing.Image.GetThumbnailImage%2A> метод <xref:System.Drawing.Image> объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Drawing.Image> объект из JPG-файла. Исходное изображение имеет ширину 640 пикселей и высоту 479 пикселей. Код создает эскиз эскиза с шириной 100 пикселей и высотой 100 пикселей.  
  
 На следующем рисунке показан эскиз изображения:  
  
 ![Снимок экрана, на котором показан эскиз выходных данных.](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
> В этом примере метод обратного вызова объявляется, но не используется. Поддерживает все версии GDI+.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, что <xref:System.Windows.Forms.Control.Paint> является параметром обработчика событий. Чтобы запустить пример, выполните следующие действия.  
  
1. Создайте новое приложение Windows Forms.  
  
2. Добавьте пример кода в форму.  
  
3. Создание обработчика для <xref:System.Windows.Forms.Control.Paint> события формы  
  
4. В обработчике `GetThumbnail` вызовите метод и передайте `e` для <xref:System.Windows.Forms.PaintEventArgs>. <xref:System.Windows.Forms.Control.Paint>  
  
5. Найдите файл изображения, эскиз которого нужно создать.  
  
6. `GetThumbnail` В методе укажите путь и имя файла для образа.  
  
7. Нажмите клавишу F5, чтобы запустить пример.  
  
     На форме появится эскиз с 100 по 100.  
  
## <a name="see-also"></a>См. также

- [Изображения, точечные рисунки и метафайлы](images-bitmaps-and-metafiles.md)
- [Работа с растровыми и векторными изображениями, значками и метафайлами](working-with-images-bitmaps-icons-and-metafiles.md)
