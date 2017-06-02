---
title: "Практическое руководство. Использование таблицы преобразования цветов | Microsoft Docs"
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
  - "таблицы преобразования цветов, использование"
  - "таблицы цветов, преобразование цветов с использованием"
  - "пользовательские цвета, создание с помощью таблиц преобразования цветов"
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Использование таблицы преобразования цветов
Преобразование — это процесс изменения цветов в изображении в соответствии с таблицей преобразования цветов.  Таблица преобразования цветов представляет собой массив объектов <xref:System.Drawing.Imaging.ColorMap>.  Каждый из объектов <xref:System.Drawing.Imaging.ColorMap> в массиве имеет свойства <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> и <xref:System.Drawing.Imaging.ColorMap.NewColor%2A>.  
  
 При рисовании изображения с помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] каждый пиксель этого изображения сравнивается с элементами массива старых цветов.  Если цвет пикселя совпадает со старым цветом из этого массива, то цвет пикселя меняется на соответствующий новый цвет.  Цвета изменяются только при отрисовке — цветовые значения самого изображения \(хранимые в объекте <xref:System.Drawing.Image> или <xref:System.Drawing.Bitmap>\) не меняются.  
  
 Чтобы нарисовать изображение с преобразованными цветами, инициализируйте массив объектов <xref:System.Drawing.Imaging.ColorMap>.  Передайте массив методу <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> объекта <xref:System.Drawing.Imaging.ImageAttributes>, после чего передайте объект <xref:System.Drawing.Imaging.ImageAttributes> методу <xref:System.Drawing.Graphics.DrawImage%2A> объекта <xref:System.Drawing.Graphics>.  
  
## Пример  
 В следующем примере объект <xref:System.Drawing.Image> создается на основе файла RemapInput.bmp.  Код создает таблицу преобразования цветов, состоящую из единственного объекта <xref:System.Drawing.Imaging.ColorMap>.  Свойство <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> объекта `ColorRemap` содержит красный цвет, а свойство <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> — синий.  Один раз изображение рисуется без преобразования цветов, а второй раз — с преобразованием.  В процессе преобразования все красные пиксели заменяются на синие.  
  
 На следующем рисунке показаны как исходное изображение \(слева\), так и преобразованное изображение \(справа\).  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Перекрашивание изображений](../../../../docs/framework/winforms/advanced/recoloring-images.md)   
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)