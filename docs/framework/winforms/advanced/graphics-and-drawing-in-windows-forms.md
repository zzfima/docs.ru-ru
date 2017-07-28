---
title: "Объекты Graphics и Drawing в Windows Forms | Microsoft Docs"
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
  - "рисование [Windows Forms]"
  - "GDI+, использование в управляемом коде"
  - "графика [Windows Forms]"
  - "графика, использование в Windows Forms"
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Объекты Graphics и Drawing в Windows Forms
Среда CLR использует расширенную реализацию интерфейса графических устройств Windows \([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]\) под названием [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  С помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] можно создавать графические элементы, рисовать текст и управлять графическими изображениями как объектами.  Интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] отличается высоким быстродействием и удобен в использовании.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] можно использовать для отрисовки графических изображений в формах и элементах управления Windows Forms.  Хотя [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] нельзя использовать непосредственно в веб\-формах, графические изображения можно выводить через элемент управления веб\-сервера Image.  
  
 В этом разделе описаны основы программирования с использованием [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  Хотя он не является полным справочником, в нем содержатся сведения об объектах <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> и <xref:System.Drawing.Color> и способах выполнения таких задач, как рисование фигур, создание текста, отображение рисунков.  Подробнее см. в справочной документации по GDI\+ в библиотеке MSDN по адресу http:\/\/msdn.microsoft.com\/library.  
  
## В этом подразделе  
 [Общие сведения о графике](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 Общие сведения об управляемых классах, связанных с графикой.  
  
 [Управляемый код GDI\+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 Сведения об управляемых классах [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Использование управляемых графических классов](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 Демонстрируется выполнение различных задач с помощью управляемых классов [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
## Ссылка  
 <xref:System.Drawing>  
 Доступ к основным графическим функциям [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 <xref:System.Drawing.Drawing2D>  
 Расширенные функциональные возможности для создания двухмерной и векторной графики.  
  
 <xref:System.Drawing.Imaging>  
 Расширенный набор графических функций [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 <xref:System.Drawing.Text>  
 Расширенный набор типографических функций [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  Классы в этом пространстве имен позволяют создавать и использовать коллекции шрифтов.  
  
 <xref:System.Drawing.Printing>  
 Функции печати.  
  
## Связанные подразделы  
 [Рисование и отрисовка пользовательского элемента управления](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)  
 Подробные сведения о способах написания кода для рисования элементов управления.