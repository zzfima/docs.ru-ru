---
title: Объекты Graphics и Drawing в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: e110203605c31f90f71c949f81c18ebf464d52eb
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505540"
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Объекты Graphics и Drawing в Windows Forms
Среда CLR использует расширенную реализацию из Windows графических устройств интерфейса (GDI) вызывается GDI +. С помощью GDI + Создание графических объектов, рисовать текст и управлять графическими изображениями как объектами. GDI + разработана для обеспечения производительности и удобства использования. GDI + можно использовать для отрисовки графических изображений в Windows Forms и элементах управления. Несмотря на то, что нельзя использовать GDI + непосредственно на веб-форм, можно отобразить графические изображения через элемент управления веб-сервера Image.  
  
 В этом разделе вы найдете описаны основы программирования GDI +. Хотя он не является полным справочником, в нем содержатся сведения об объектах <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> и <xref:System.Drawing.Color> и способах выполнения таких задач, как рисование фигур, создание текста, отображение рисунков. Дополнительные сведения см. в разделе [GDI + ссылку](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).  
  
 Если вы хотите немедленно приступить к работе, см. статью [Приступая к программированию графики](getting-started-with-graphics-programming.md). Она содержит разделы, посвященные использованию кода для рисования линий, фигур, текста и других элементов в формах Windows Forms.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Общие сведения о графике](graphics-overview-windows-forms.md)  
 Общие сведения об управляемых классах, связанных с графикой.  
  
 [Управляемый код GDI+](about-gdi-managed-code.md)  
 Сведения об управляемых классах GDI +.  
  
 [Использование управляемых графических классов](using-managed-graphics-classes.md)  
 Демонстрирует, как для завершения различных задач с помощью GDI + управляемые классы.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Drawing>  
 Предоставляет доступ к основным графическим функциям GDI +.  
  
 <xref:System.Drawing.Drawing2D>  
 Расширенные функциональные возможности для создания двухмерной и векторной графики.  
  
 <xref:System.Drawing.Imaging>  
 Предоставляет расширенный набор графических функций GDI +.  
  
 <xref:System.Drawing.Text>  
 Предоставляет расширенный набор типографических функций GDI +. Классы в этом пространстве имен позволяют создавать и использовать коллекции шрифтов.  
  
 <xref:System.Drawing.Printing>  
 Функции печати.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Рисование и отрисовка пользовательского элемента управления](../controls/custom-control-painting-and-rendering.md)  
 Подробные сведения о способах написания кода для рисования элементов управления.
